# 1. Installation

### Conda로 Python 3.7 설치

1. Conda를 설치합니다.
2. Conda 명령 프롬프트를 엽니다.
3. 다음 명령어를 실행하여 Python 3.7을 설치합니다.

```bash
conda install -n env_name python=3.7
```
4. conda enviroment 를 활성화 합니다.
```bash
conda activate env_name
```
### Pip로 requirement.txt 설치

1. 다음 명령어를 실행하여 requirements.txt 파일의 패키지를 설치합니다.

```bash
pip install -r requirements.txt
```

# 2. Get gt json file

1. mediapipe 디렉토리로 이동해서, keypoints라는 directory를 생성합니다.
```bash
   cd mediapipe
   mkdir keypoints
```
2. keypoints 폴더 안에 학습 영상을 위치시킵니다.
3. 학습 영상을 gt.mp4, 비교 영상을 prac.mp4로 이름을 변경해 줍니다.
4. cd mediapipe 를 입력해, mediapipe 디렉토리(폴더)로 이동합니다. 그리고, extract_gt_keypoints.py를 실행하여, 정답 json을 얻습니다.
   ```bash
    cd mediapipe
    python extract_gt_keypoints.py
   ```
5. python compare_norm_veccos_10_framep.py 테스트 해봅니다.
   ```bash
    python compare_norm_veccos_10frame.py
   ```

# 3. gt file streamlit으로 옮기기

1. streamlit 디렉토리로 이동합니다. (cd ../streamlit)
   ```bash
   cd ../streamlit
   ```
2. mediapipe/save_json 폴더 안에 있는 gt.mp4 폴더를 
    통째로 streamlit/dataset/json 폴더 안에 복사 붙여넣기 합니다.
    ```bash
    cp -R ../mediapipe/save_json/gt.mp4 dataset/json/gt.mp4
    ```
3. streamlit/dataset/video 에 정답 영상을 복사 붙여넣기 합니다.
   ```bash
   cp ../mediapipe/keypoints/gt.mp4 dataset/video
   ```

# 4. 실행

1. streamlit run --server.port 8080 --server.enableCORS false app.py 를 실행합니다.
   ```bash
    streamlit run --server.port 8080 --server.enableCORS false app.py
   ```
2. 크롬 창을 켜고, 웹 주소에 localhost:8080을 입력합니다.
3. 창이 뜨면, Please select Music 에서 gt를 선택합니다.  
4. Brouse files에서 prac.mp4를 선택합니다. 




