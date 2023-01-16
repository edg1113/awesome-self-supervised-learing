# MoCo
 
- Title: Momentum Contrast for Unsupervised Visual Representation Learning
- Publication: CVPR, 2020
- Link: [[paper](https://arxiv.org/abs/1911.05722)] [[code](https://github.com/facebookresearch/moco)]

## Review
[SungEun] MoCo는 Contrastive Learning이 Dynamic dictionary system으로 보고 기존의 memory bank 방식이나 end-to-end방식과는 다르게
queue와 momentum encoder를 이용하여 일관성있는 dynamic dictionary를 구축하여 visual representation을 얻을 수 있다.
스터디를 통해서 잘 몰랐었던 기존 memory bank를 이용한 SSL의 문제를 알게되었고 end-to-end 방식과 memory bank, MoCo의 차이를 좀더 세세하게 알게 되었다. 

[DongHyun] MOCO는 기존 end-to-end 와 memory bank 방식이 가지는 메모리 부분에서의 단점을 해결하기 위하여 고안된 방법으로 momentum encoder를 활용한다. 
여기에서 이 momentum encoder를 학습하는 방식이 흥미로웠는데 메인 encoder가 학습한 parameter들의 일부만 전달받는식으로 학습을 대신하게 된다. 
이런 방식으로 정확도를 높인다는 것이 직관적으로 이해가 되는 부분은 아니었지만 추후에 실험을 해보면서 이해하게된다면 다른 연구에서 사용하는데에 도움이 될 것 같다. 
