# SimCLR
 
- Title: A Simple Framework for Contrastive Learning of Visual Representations
- Publication: ICML, 2020
- Link: [[paper](https://arxiv.org/abs/2002.05709)] [[code](https://github.com/sthalles/SimCLR)]

## Review
**[SungEun]** SimCLR은 contrastive learning을 통해 visual representation을 얻을 수 있는 간단한 framework로 Original image에서 Data augmentation을 통해 Transform된 이미지를 $x_i$, $x_j$로 나누어 encode를 통과해 representation을 얻고 non-linear fully connected layer를 거쳐 나온 $z_i$와 $z_j$의 contrastive loss를 이용해 maximize agreement하게 학습하는 방식으로 visual representaiton을 얻을수 있다. 또한 SimCLR을 학습할 때 batch size를 키울수록 충분한 양의 negative sample을 확보할 수 있어 모델의 성능을 증가시키는 경향을 보인다. 혼자서 공부할 때 이해안되는 용어나 내용들이 많았는데 스터디를 통해 SimCLR에 대해 잘못이해했던 부분과 잘모르는 부분을 같이 알 수 있었다.

**[DongHyun]** 이번 주 스터디는 Self-supervised-learning 스터디의 첫 번째 논문 리뷰 스터디였다. 두 개의 contrasitive learning 방법론에 대해서 논문 리뷰를 진행했다. SSL에 대해서 처음 배우다보니 논문에서 이전의 연구 결과라며 소개한 NCE loss 등에 대한 기초 지식 학습이 조금 부족했던 것 같다. 수식적인 이해는 추후에 보충해야 할 것 같다. SimCLR은 두 개의 encoder를 사용하여 서로 다른 augmentation에 대해 representation을 생성 한 다음 두 representation의 agrement를 최대한 가깝게 만들도록 학습시킨다. 이 과정에서 encoder 이후에 2개의 레이어를 가진 학습 가능한 MLP 계층이 존재하여 학습을 도운다. 이 추가적인 레이어가 어떠한 역할을 하는지는 스터디 이후에 추가적으로 학습해야할 것 같다. 

**[Seungmin]**
이전의 SSL방법들은 물론 성능이 좋아지긴했으나, supervised learning과 견줄정도의 성능을 내지는 못했다. Contrastive learning의 대표격인 MoCo는 Dynamic dictionary로 memory bank문제를 어느정도 해결할 수 있었지만, 여전히 메모리 문제가 나음. SimCLR은 `Stochastic Data Augmentation`, `Single Encoder and Projection`, `Contrastive Loss Function` 을 이용해 이를 해결해보고자 함.
- Stochastic data augmentation: strong and various 하면서 stochastic하게 data augmentation을 하면서 negative pair를 많이, 잘 만들어 냄
- Single encoder and projection: query, key 이미지를 하나의 encoder를 사용함으로써 architecture를 더 간결하게 만들 수 있었고, projection layer를 마지막에 추가해줘서 더 풍부한 feature extraction 가능
- Contrastive loss function: contrastive learning에 맞게 새로운 Loss function을 제시

SimCLR은 SSL중 contrastive learning(CL)을 대표할만한 간단한 아키텍쳐를 제시하여 앞으로의 CL기법을 연구하는데 많은 intuition이 될 것 같음. 다만 *depend on large batch size and negative pair*라는 문제가 남아있음.