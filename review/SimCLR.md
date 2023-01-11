# SimCLR
 
- Title: A Simple Framework for Contrastive Learning of Visual Representations
- Publication: ICML, 2020
- Link: [[paper](https://arxiv.org/abs/2002.05709)] [[code](https://github.com/sthalles/SimCLR)]

## Review
[SungEun] SimCLR은 contrastive learning을 통해 visual representation을 얻을 수 있는 간단한 framework로 Original image에서 Data augmentation을 통해 Transform된 이미지를 $x_i$, $x_j$로 나누어 encode를 통과해 representation을 얻고 non-linear fully connected layer를 거쳐 나온 $z_i$와 $z_j$의 contrastive loss를 이용해 maximize agreement하게 학습하여 visual representaiton을 얻을수 있다. 또한 SimCLR을 학습할 때 batch size를 키울수록 충분한 양의 negative sample을 확보할 수 있어 모델의 성능을 증가시키는 경향을 보인다. 혼자서 공부할 때 이해안되는 용어나 내용들이 많았는데 스터디를 통해 SimCLR에 대해 잘못이해했던 부분과 잘모르는 부분을 같이 알 수 있었다.
