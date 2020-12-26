### PyTorch Image to Image Translation

* 작성자: 나동빈(Dongbin Na / dongbinna@postech.ac.kr)
* 본 코드는 POSTECH의 **CSED703G 수업** 과제로 작성한 코드입니다.

### DCGAN: Deep Convolutional Generative Adversarial Networks (ICLR 2016)

* DCGAN 학습/평가 전체 소스코드는 Google Colab을 이용해 실행할 수 있도록 작성했습니다.
* 성능 향상을 위하여 광범위한 실험을 진행했습니다.
* 현존하는 색상(color) 얼굴 마스크 이미지 데이터셋은 개수가 부족하고 마스크 표본이 적습니다.
* 인위적으로 생성된 <b>흑백(grayscale) 얼굴 마스크 이미지 데이터셋</b>을 이용하여 좋은 결과를 얻을 수 있었습니다.
* 데이터셋의 크기가 작으며 개수가 충분한 경우에는 오히려 <b>단순한 Upsampling이 좋은 성능</b>을 낼 수 있었습니다.
    * 원본 논문의 Transposed Convolution을 이용하는 것보다 모델 용량 대비 효과적이었습니다.
* 자세한 하이퍼 파라미터는 각 소스코드에서 자세히 확인 가능합니다.

#### [Upsampling DCGAN for Face Mask](Upsampling_DCGAN_for_Face_Mask_(Grayscale).ipynb)

* 학습용 데이터셋: 커스텀 <b>Face Mask (Grayscale)</b>
* <b>얼굴(Face) 이미지 생성</b>

<img src="https://user-images.githubusercontent.com/16822641/103152412-07385e80-47cb-11eb-9024-719306c34f40.png" width="60%">

* <b>노이즈 벡터 연산(Noise Vector Arithmetic)</b>

<img src="https://user-images.githubusercontent.com/16822641/103152508-0b18b080-47cc-11eb-9201-9400158cb17b.png" width="80%">

* <b>노이즈 벡터 보간법(Noise Vector Interpolation)</b>

<img src="https://user-images.githubusercontent.com/16822641/103152524-2edbf680-47cc-11eb-8e25-07963dc4ddc5.png" width="80%">

* **[학습된 생성자(Generator) 모델 다운로드 (18MB)](https://postechackr-my.sharepoint.com/:u:/g/personal/dongbinna_postech_ac_kr/Eb6v0gHgcg1HitX2lqLzkbUB6hr9RZ0LfDjfFaSXrcSgLQ)**
* **[학습된 판별자(Discriminator) 모델 다운로드 (6MB)](https://postechackr-my.sharepoint.com/:u:/g/personal/dongbinna_postech_ac_kr/ERAThboZ0c1Lh1RGQGxrkToB6PxE18nBQA5XR0Zj-oj4kQ)**

#### [Transposed DCGAN for Face Mask](Transposed_DCGAN_for_Face_Mask_(Grayscale).ipynb)

* 학습용 데이터셋: 커스텀 <b>Face Mask (Grayscale)</b>
* <b>얼굴(Face) 이미지 생성</b> 예시

<img src="https://user-images.githubusercontent.com/16822641/103152543-5f239500-47cc-11eb-848d-49d1c3cf4547.png" width="60%">

* <b>노이즈 벡터 연산(Noise Vector Arithmetic)</b>

<img src="https://user-images.githubusercontent.com/16822641/103152572-a27e0380-47cc-11eb-9145-10f5ee517744.png" width="80%">

* <b>노이즈 벡터 보간법(Noise Vector Interpolation)</b>

<img src="https://user-images.githubusercontent.com/16822641/103152552-6c408400-47cc-11eb-881f-a729a1c0227a.png" width="80%">

* **[학습된 생성자(Generator) 모델 다운로드 (23MB)](https://postechackr-my.sharepoint.com/:u:/g/personal/dongbinna_postech_ac_kr/EcHLK3-S0sNHrm5FN9ZMjr8BxIc8gb3Byb3oOQBjyObIgg)**
* **[학습된 판별자(Discriminator) 모델 다운로드 (6MB)](https://postechackr-my.sharepoint.com/:u:/g/personal/dongbinna_postech_ac_kr/EZ2EObj0zDFHoxv4vEBrLPwBJ3ZBbF2ut_meNB8Pc-wkhQ)**

### Pix2Pix: Image-to-Image Translation with Conditional Adversarial Networks (CVPR 2017)

* Pix2Pix 학습/평가 전체 소스코드는 Google Colab을 이용해 실행할 수 있도록 작성했습니다.
* 성능 향상을 위하여 광범위한 실험을 진행했습니다.
* <b>L1 손실(loss)</b>을 사용했을 때가 조금 더 성능이 좋습니다.
    * 페어링 된(paired) 정답 데이터의 방향을 알려주는 L1 손실이 추가된다는 점에서 CycleGAN보다 성능이 좋습니다.
* 생성자(generator)는 U-Net 구조를 활용하여 이미지의 크기에 맞게 깊은 레이어를 유지하도록 합니다.
* 커스텀 데이터셋으로는 <b>색상 입히기(colorization) 데이터셋</b>을 수집하여 활용하였습니다.
* 자세한 하이퍼 파라미터는 각 소스코드에서 자세히 확인 가능합니다.

#### [Pix2Pix for Facades](Pix2Pix_for_Facades.ipynb)

* 학습용 데이터셋: <b>Facades</b>
* <b>Image to Image Translation</b> 예시

<img src="https://user-images.githubusercontent.com/16822641/103151501-f0d9d500-47c1-11eb-9b6a-8247db6d2fdb.png" width="80%">

* **[학습된 생성자(Generator) 모델 다운로드 (212MB)](https://postechackr-my.sharepoint.com/:u:/g/personal/dongbinna_postech_ac_kr/EQPOZG2WXrlHirX5l8SHM9MBVcE0pLoIAdYwd3-hWXm73Q)**
* **[학습된 판별자(Discriminator) 모델 다운로드 (10MB)](https://postechackr-my.sharepoint.com/:u:/g/personal/dongbinna_postech_ac_kr/EYlJJGhQ5OFKp14jS_zGy8kBekJSkIe3ioN8LFIk59oa6A)**

#### [Pix2Pix for Colorization](Pix2Pix_for_Colorization.ipynb)

* 학습용 데이터셋: <b>Landscape Colorization</b>
* <b>Image to Image Translation</b> 예시 (Epoch 120/200까지 학습되었을 때)

<img src="https://user-images.githubusercontent.com/16822641/103152944-2685ba80-47d0-11eb-8259-5e816dccfc18.png" width="80%">

* **[학습된 생성자(Generator) 모델 다운로드 (163MB)](https://postechackr-my.sharepoint.com/:u:/g/personal/dongbinna_postech_ac_kr/EUy5gLVjz7dPq9GuTD8YL74BK5hPq5Gujb2M5XINR5v0Lg)**
* **[학습된 판별자(Discriminator) 모델 다운로드 (10MB)](https://postechackr-my.sharepoint.com/:u:/g/personal/dongbinna_postech_ac_kr/EX6UNA7hk2ROgjx34l1D_u4BiNvRSCWZMbJwbUfc1DW0AA)**

### CycleGAN: Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks (ICCV 2017)

* CycleGAN 학습/평가 전체 소스코드는 Google Colab을 이용해 실행할 수 있도록 작성했습니다.
* 성능 향상을 위하여 광범위한 실험을 진행했습니다.
* <b>페어링이 되지 않은(unpaired) 데이터셋</b>을 사용할 수 있지만 학습에 오랜 시간이 걸린다는 단점이 있습니다.
* 개인적으로 가장 큰 문제는 생성자(Generator)와 판별자(Discriminator)가 각각 2개씩 필요하다는 것입니다.
    * 이 문제는 StarGAN의 아이디어를 이용해 개선할 수 있을 것으로 보입니다.
* 생성자(generator)는 ResNet 기반의 구조를 활용하여 이미지의 크기에 맞게 깊은 레이어를 유지하도록 합니다.
* 커스텀 데이터셋으로는 <b>풍경화 색상 입히기(landscape colorization) 데이터셋</b>을 수집하여 활용하였습니다.
    * 이 경우 고의적으로 페어링이 되지 않은(unpaired) 샘플링을 수행하여 학습했습니다.
* 자세한 하이퍼 파라미터는 각 소스코드에서 자세히 확인 가능합니다.
* CycleGAN의 경우 배치 크기를 크게 설정하기 어렵다는 점에서 학습 시간이 매우 많이 필요할 수 있습니다.

#### [CycleGAN for Horse2Zebra](CycleGAN_for_Horse2Zebra_Translation.ipynb)

* 학습용 데이터셋: <b>Horse2Zebra</b>
* <b>Image to Image Translation</b> 예시 (Epoch 30/200까지 학습되었을 때)

<img src="https://user-images.githubusercontent.com/16822641/103153377-6ef2a780-47d3-11eb-8a69-1bf5abd46480.png" width="80%">

* **[Epoch 30/200까지 학습된 생성자(Generator) A to B 모델 다운로드 (43MB)](https://postechackr-my.sharepoint.com/:u:/g/personal/dongbinna_postech_ac_kr/EXMlQ_FrekdGo-A-DMPcwfsBatwaAfVJ1p2HCegX-0gacw)**
* **[Epoch 30/200까지 학습된 생성자(Generator) B to A 모델 다운로드 (43MB)](https://postechackr-my.sharepoint.com/:u:/g/personal/dongbinna_postech_ac_kr/EfU1PMf8r39Ku_YJtkhidacBSu963Gr7d-8VKgSuSHWMCA)**
* **[Epoch 30/200까지 학습된 판별자(Discriminator) A 모델 다운로드 (10MB)](https://postechackr-my.sharepoint.com/:u:/g/personal/dongbinna_postech_ac_kr/Ee2nFja4w3NHluFU1n43Z6oBpIM4sFX0GsgpoZdBpxGS7A)**
* **[Epoch 30/200까지 학습된 판별자(Discriminator) B 모델 다운로드 (10MB)](https://postechackr-my.sharepoint.com/:u:/g/personal/dongbinna_postech_ac_kr/EUgH2KGMRUZNsPYKrTGkC2wBUVN1ksNuvYKheYE37PAQIA)**

#### [Pix2Pix for Colorization](CycleGAN_for_Colorization_Translation.ipynb)

* 학습용 데이터셋: <b>Landscape Colorization</b>
* <b>Image to Image Translation</b> 예시 (Epoch 30/200까지 학습되었을 때)

<img src="https://user-images.githubusercontent.com/16822641/103153724-f3dec080-47d5-11eb-9cb6-b0d20b2963d5.png" width="80%">

* **[Epoch 30/200까지 학습된 생성자(Generator) A to B 모델 다운로드 (43MB)](https://postechackr-my.sharepoint.com/:u:/g/personal/dongbinna_postech_ac_kr/EeFi-WAmh35DmKBvomFOxw4BM9nOycKNbAH5k0H6UKK7Xw)**
* **[Epoch 30/200까지 학습된 생성자(Generator) B to A 모델 다운로드 (43MB)](https://postechackr-my.sharepoint.com/:u:/g/personal/dongbinna_postech_ac_kr/EUx3PR7qdDZBkANFu4-cTQ0Bmr2mMm8ffSop0N5MgPHeGQ)**
* **[Epoch 30/200까지 학습된 판별자(Discriminator) A 모델 다운로드 (10MB)](https://postechackr-my.sharepoint.com/:u:/g/personal/dongbinna_postech_ac_kr/Ef_kALQH0e5BsllUDxUQrTIBVvk41lPzPbXOl3SV1y60vw)**
* **[Epoch 30/200까지 학습된 판별자(Discriminator) B 모델 다운로드 (10MB)](https://postechackr-my.sharepoint.com/:u:/g/personal/dongbinna_postech_ac_kr/EUqZwDvdyc9MvzeXIdftYdQBN9YWN47vmVLsI1HxcYhczA)**
