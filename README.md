# 음성인식 인공지능 경진대회

- [문제3 음성 인식(자유대화) 데이터셋 설명](#문제-3-음성인식-자유대화-dataset-설명)
- [문제4 음성 인식(명령어) 데이터셋 설명](#문제-4-음성인식-명령어-dataset-설명)
- [문제5 음성 인식(한국어방언) 데이터 셋명](#문제-5-음성인식-한국어방언-dataset-설명)

## 대회 규칙

- **주제**
  - 한국어 음성을 텍스트로 변환하는 인공지능 개발
- **평가**
  - CER(Character Error Rate) 제1지표
  - WER(Word Error Rate) 제2지표
  - 리더보드에는 CER만 표시
  - 최종평가시 동점인 경우 차순위 지표 우수팀이 상위
  - 최종 동점이 발생한 경우 먼저 제출한 팀이 상위
- **NSML GPU 지원**
  - Tesla V100-SXM2-32GB 2개 (하나의 task에 2개 사용 가능)
- **<u>법적 제약이 없는 외부 데이터 및 사전 학습 모델 사용 가능(대회 종료 후 코드 제출시 함께 제출)</u>**

## 문제 3 **[음성인식-자유대화 Dataset 설명]**

- 음성 파일과 매칭되는 text를 추론

  | 전체 크기 |                 파일수                  | NSML 데이터셋 이름 |
  | :-------: | :-------------------------------------: | :----: |
  |  54.5GB  | train_data(268,928)<br>test_data(10,000) | final_stt_1 |

### Train Dataset

- `root_path/train/train_data/`(268,928개의 wav 파일 \*확장자 없는 레이블 형태)

  ```
  idx0000001
  idx0000002
  idx0000003
  idx0000004
  ...
  idx0268925
  idx0268926
  idx0268927
  idx0268928
  ```

### Train Label

`root_path/train/train_label`

- `train_label (DataFrame 형식, 268,928rows)`

  - columns - `["file_name", "text"]`

  - `file_name` - train_data 폴더에 존재하는 wav파일명 (ex. idx000001)

  - `text` - train_data 폴더에 존재하는 wav파일과 매칭되는 Text 정보 (ex. 훈민정음에 스며들다)

### Test Dataset

- `root_path/test/test_data/`(10,000개의 wav 파일 \*확장자 없는 레이블 형태/ train_data와 파일명 형식이 다름에 주의)

  ```
  idx_0000001
  idx_0000002
  idx_0000003
  idx_0000004
  ...
  idx_0009997
  idx_0009998
  idx_0009999
  idx_0010000
  ```

### Test Label

- `root_path/test/test_label` (참가자 접근 불가)

- `test_label (DataFrame 형식, 10,000rows)`

  - columns = `["file_name", "text"]`

  - `file_name` - test_data 폴더에 존재하는 wav파일명 (ex. idx_000001)

  - `text` - test_data 폴더에 존재하는 wav파일과 매칭되는 Text 정보 (ex. 훈민정음에 스며들다)



## 문제 4 **[음성인식-명령어 Dataset 설명]**

- 음성 파일과 매칭되는 Text를 추론(aka.받아쓰기)

  | 전체 크기 |                  파일수                  |  NSML 데이터셋 이름 |
  | :-------: | :--------------------------------------: | :-----: |
  |   62GB    | train_data(197,146)<br>test_data(10,000) | final_stt_2 |

### Train Dataset

- `root_path/train/train_data/`(197,146개의 wav 파일 \*확장자 없는 레이블 형태)

  ```
  idx0000001
  idx0000002
  idx0000003
  idx0000004
  ...
  idx0197143
  idx0197144
  idx0197145
  idx0197146
  ```

### Train Label

- `root_path/train/train_label`

- `train_label (DataFrame 형식, 197,146rows)`

  - columns - `["file_name", "text"]`

  - `file_name` - train_data 폴더에 존재하는 wav파일명 (ex. idx000001)

  - `text` - train_data 폴더에 존재하는 wav파일과 매칭되는 text 정보 (ex. 훈민정음에 스며들다)

### Test Data

- `root_path/test/test_data/`(10,000개의 wav 파일 \*확장자 없는 레이블 형태 / train_data와 파일명 형식이 다름에 주의)

  ```
  idx_0000001
  idx_0000002
  idx_0000003
  idx_0000004
  ...
  idx_0009997
  idx_0009998
  idx_0009999
  idx_0010000
  ```

### Test Label

- `root_path/test/test_label` (참가자 접근 불가)

- `test_label (DataFrame 형식, 10,000rows)`

- columns = `["file_name", "text"]`

  - `file_name`- test_data 폴더에 존재하는 wav파일명 (ex. idx_000001)

  - `text` - test_data 폴더에 존재하는 wav파일과 매칭되는 Text 정보 (ex. 훈민정음에 스며들다)

  
---


## 문제 5 **[음성인식-한국어방언 Dataset 설명]**

- 음성 파일과 매칭되는 text를 추론

  | 전체 크기 |                 파일수                  | NSML 데이터셋 이름 |
  | :-------: | :-------------------------------------: | :----: |
  |  65.42GB  | train_data(1,059)<br>test_data(60) | final_stt_3 |

### Train Dataset

- `root_path/train/train_data/wav`(1,059개의 wav 파일 \*확장자 없는 레이블 형태)

  ```
  DJSX20002450
  DJSX20002451

  ...
  DKSR20000888
  DKSR20000889
  ```
  
- `root_path/train/train_data/info`(1,059개의 json 파일 \*확장자 없는 레이블 형태)

- [경상도 발화 데이터](https://aihub.or.kr/sites/default/files/2021-06/14.%20%5B%ED%95%9C%EA%B5%AD%EC%96%B4%20%EB%B0%A9%EC%96%B8%20%EA%B3%BC%EC%A0%9C%5D%20%ED%95%9C%EA%B5%AD%EC%96%B4%20%EB%B0%A9%EC%96%B8%20%EB%B0%9C%ED%99%94%20%EB%8D%B0%EC%9D%B4%ED%84%B0%28%EA%B2%BD%EC%83%81%EB%8F%84%29.pdf)
- [전라도 발화 데이터](https://aihub.or.kr/sites/default/files/2021-06/15.%20%5B%ED%95%9C%EA%B5%AD%EC%96%B4%20%EB%B0%A9%EC%96%B8%20%EA%B3%BC%EC%A0%9C%5D%20%ED%95%9C%EA%B5%AD%EC%96%B4%20%EB%B0%A9%EC%96%B8%20%EB%B0%9C%ED%99%94%20%EB%8D%B0%EC%9D%B4%ED%84%B0%28%EC%A0%84%EB%9D%BC%EB%8F%84%29.pdf)



### Train Label

`root_path/train/train_label`(DataFrame 형식, 1,059개의 rows)

  - columns - `["file_name", "text"]`

  - `file_name` - train_data 폴더에 존재하는 wav파일명 (ex. DKSR20000888)

  - `text` - train_data/wav 폴더에 존재하는 wav파일과 매칭되는 Text 정보 (train_data/info 파일(json)의 `dialect_form`을 띄어쓰기(' ')로 이어붙여 생성하였음)

### Test Dataset

- `root_path/test/test_data/`(60개의 wav 파일 \*확장자 없는 레이블 형태)

  ```
  DJDD20000306
  DJDD20000307
  ...
  DKSR20006835
  DKSR20006836
  ```

### Test Label

- `root_path/test/test_label` (참가자 접근 불가)

- `test_label (DataFrame 형식, 60 rows)`

  - columns = `["file_name", "text"]`

  - `file_name` - test_data 폴더에 존재하는 wav파일명 (ex. DJDD20000306)

  - `text` - test_data 폴더에 존재하는 wav파일과 매칭되는 Text 정보 (json 파일의 `dialect_form`을 띄어쓰기(' ')로 이어붙여 생성하였음)
