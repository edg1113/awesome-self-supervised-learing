# MoCo
 
- Title: Momentum Contrast for Unsupervised Visual Representation Learning
- Publication: CVPR, 2020
- Link: [[paper](https://arxiv.org/abs/1911.05722)] [[code](https://github.com/facebookresearch/moco)]

## Review
**[SungEun]** MoCo는 Contrastive Learning이 Dynamic dictionary system으로 보고 기존의 memory bank 방식이나 end-to-end방식과는 다르게
queue와 momentum encoder를 이용하여 일관성있는 dynamic dictionary를 구축하여 visual representation을 얻을 수 있다.
스터디를 통해서 잘 몰랐었던 기존 memory bank를 이용한 SSL의 문제를 알게되었고 end-to-end 방식과 memory bank, MoCo의 차이를 좀더 세세하게 알게 되었다. 

**[DongHyun]** MOCO는 기존 end-to-end 와 memory bank 방식이 가지는 메모리 부분에서의 단점을 해결하기 위하여 고안된 방법으로 momentum encoder를 활용한다. 
여기에서 이 momentum encoder를 학습하는 방식이 흥미로웠는데 메인 encoder가 학습한 parameter들의 일부만 전달받는식으로 학습을 대신하게 된다. 
이런 방식으로 정확도를 높인다는 것이 직관적으로 이해가 되는 부분은 아니었지만 추후에 실험을 해보면서 이해하게된다면 다른 연구에서 사용하는데에 도움이 될 것 같다. 

**[SeungMin]** 이전의 memory bank방식은 메모리 사용량이 커지는 문제뿐 아니라, feature extractor가 weight을 업데이트하고나면 동시에 새로운 feature를 뽑지 못하는 문제가 있었음. 그래서 메모리 문제를 해결하기 위해 random sampling 방식을 사용했는데, 이 역시도 한번도 학습에 사용하지 못하는 데이터가 나올 수 있다는 문제가 있음.
따라서 MoCo는 `Dynamic dictionary`, `Moving average encoder` 방식을 제안함.
- Dynamic dictionary: Que방식으로 sampling하여, random sample의 문제점을 해결할 수 있고, 메모리 효율성을 높일 수 있음. InfoNCE라는 loss function을 사용하여, query와 key의 distance를 더 잘 학습함
- Moving average encoder: 보통은 pretrainede된 모델에서 query를 만들어서 memory bank를 만들었는데, query encoder에서 moving average를 통해 key encoder는 back propagation을 하지는 않지만, 학습된 weight을 가지게 됌.

MoCo는 이전 세대의 문제점과 장점을 조화롭게 녹여낼 수 있었지만, dynamic dictionary는 여전히 메모리 문제를 가지고 있었고, 성능이 만족스럽게 보이지 않음.