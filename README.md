# 크롤링 프로젝트 <김범주>

### 이미지 학습을 통한 음악 추천 사이트 만들기 ###

<프로젝트 요약> 

이미지 학습을 통한 음악 추천 사이트는 이미지를 업로딩 할 시 사진의 분위기나 감정을 파악하여 음악을 추천해주시는 서비스입니다.이 프로그램을 이용하면 사진 업로드 시 분위기에 맞는 음악을 자동적으로 선정해주어 원하는 음악을 들을 수 있습니다. 동작 방식은 이미지를 파일 업로딩 하는 부분에 등록 후 미리 제작해 둔 이미지 분석 모델을 통해 업로드 된 이미지의 분위기를 선정하여 크롤링 된 멜론(Melon) 음악 사이트의 Link주소로 들어가 선정된 노래를 들을 수 있습니다. 또한 streamlit 모듈을 통해 파이썬 상에서 웹 사이트를 작성하여 파일 업로딩, 예측 결과 값을 도출하도록 구성하였습니다.

## <프로젝트 사용 방법>

프로젝트 파일로는 먼저 이미지와 멜론 플레이리스트를 크롤링한 Crawling_img, Crawling_melon.ipynb 파일이 있습니다. Crawling_img은 크롤링 코드를 통해 원하는 이미지를 구글에서 검색하여
crawling_img 파일에 저장할 수 있습니다. 이를 통해 딥러닝 모델 학습에 필요한 이미지들을 크롤링하였습니다. 


Crawling_melon.ipynb 파일은 멜론의 html 형식을 파악한 후 css-selector를 이용하여 동적 크롤링을 진행하였습니다. 그 후 크롤링한 #행복,슬픔 태그의 노래들을 Pandas DataFrame을 통해 행복한 노래, 슬픈 노래.csv로 작성하였습니다. 


CNN1.ipynb은 Crawling_img에서 크롤링한 행복한 이미지, 슬픈 이미지를 학습시켜 label(정답 값)을 통해 슬픔/0, 행복/1로 분류하였습니다.


app.py 파일은 Python 개발 환경에서 웹 페이지를 구현할 수 있는 Streamlit 모듈을 사용하여 간단하게 웹 페이지를 구성한 후 모델 분석 값을 통해 csv파일을 불러올 수 있도록 구성하였습니다.

<< Streamlit 사용 방법 >>
## streamlit run app.py 
