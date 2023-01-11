# MoCo
 
- Title: Momentum Contrast for Unsupervised Visual Representation Learning
- Publication: CVPR, 2020
- Link: [[paper](https://arxiv.org/abs/1911.05722)] [[code](https://github.com/facebookresearch/moco)]

## Review
[SungEun] MoCo는 Contrastive Learning이 Dynamic dictionary system으로 보고 기존의 memory bank 방식이나 end-to-end방식과는 다르게
queue와 momentum encoder를 이용하여 일관성있는 dynamic dictionary를 구축하여 visual representation을 얻을 수 있다.
스터디를 통해서 잘 몰랐었던 기존 memory bank를 이용한 SSL의 문제를 알게되었고 end-to-end 방식과 memory bank, MoCo의 차이를 좀더 세세하게 알게 되었다. 
