## 소리 데이터 분석 대표
1. 음성 인식 (Speech Recognition)
2. 오디오 분류 (Audio Classification)
3. 오디오 캡셔닝 (Audio Captioning)

## 소리 데이터 분석의 전체적 프로세스
Sound -> waveform -> feature -> model -> applocation

### Sound Data
- 세기 (소리의 크기)
- 높낮이 (소리의 높고 낮음)
- 음색 (소리의 색상)

#### 주파수(Hz)
- 진폭 (Amplitude)
- 주기 (Cycle)
- 파장의 길이 (Wavelength)

소리를 컴퓨터에 입력 시키기 위해 음파를 숫자로 표현할 필요가 있음  
-> 샘플링 레이트(Sampling Rate)

#### Feature Extraction
파동 = Time Domain + Freq. Domain  
다양한 특성 정보를 추출하기 위한 방법론이 존재  
- 스펙트럼 (Spectrum)
- 스펙트로그램 (Spectrogram)
- 스칼로그램 (Scalogram)
- MFCC
- FFT/STFT
- CQT
- ...

##### Representative Extraction
1. 스펙트럼 (Spectrum)
파동의 시간 영역을 주파수 영역으로 변환  
-> 음향 신호를 주파수, 진폭으로 분석하여 보여줌

2. 멜 스펙트로그램 (Mel Spectrogram)
주파수 특성이 시간에 따라 달라지는 오디오를 분석하기 위한 특징 추출 기법  
인간의 청각 영역을 반영한 **mel scale** 을 적용  
프레임의 길이와 슬라이딩 범위를 하이퍼 파라미터로 설정  

3. MFCC (Mel-Frequency Cepstral Coefficient)
멜 스펙트럼(Mel Spectrum)에서 켑스트럴(Ceptral) 분석을 통해 추출된 값  
-> 배음 구조를 유추할 수 있도록 도와주는 분석  
로그 멜 스펙트럼에 역푸리에 변환(Inverse Fourier Tranform)을 적용  
-> 주파수 정보의 상관 관계가 높은 문제를 해소

#### 추출된 특징 사용
- 고차원 특징이기에 머신러닝 모델 적용을 위해 기술 통계량을 사용
- 딥러닝의 경우 특징 고유의 값이나 히트맵을 이미지로 변환하여 사용 (CNN)

#### 데이터 증강 기법(Data Augmentation)
- Adding noise
- Shifting
- Stretching