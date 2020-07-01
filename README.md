# nanum_font
네이버 나눔 폰트를 저장하여 불러오기 위한 저장소입니다. 캐글(Kaggle)에서 `matplotlib`나 `seaborn` 사용할 때 손쉽게 한글폰트를 불러와서 사용할 수 있습니다.
[Nanum Gothic, Google Fonts](https://fonts.google.com/specimen/Nanum+Gothic#standard-styles)에서 다운로드한 폰트 파일입니다.


## 설치 순서 

1. 저장소를 복사합니다
```
  !git clone https://github.com/namepen/nanum_font.git
```

2. 폰트 파일의 경로를 지정하여 font_manager에 추가합니다. [how to set up a custom font with custom path to matplotlib global font?, stackoverflow](https://stackoverflow.com/questions/35668219/how-to-set-up-a-custom-font-with-custom-path-to-matplotlib-global-font)의 내용을 참고하였습니다.

```
  import matplotlib.pyplot as plt
  import matplotlib.font_manager as font_manager

  font_dirs = ['nanum_font', ] # 설치된 경로를 넣습니다. 
  font_files = font_manager.findSystemFonts(fontpaths=font_dirs)
  font_list = font_manager.createFontList(font_files)
  font_manager.fontManager.ttflist.extend(font_list)

  mpl.rcParams['font.family'] = 'NanumGothic'
```

