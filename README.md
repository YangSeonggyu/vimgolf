# 오픈소스SW개론 과제(vimgolf)
20195122_양성규
## 목차
1. [vimgolf란](#vimgolf란)
2. [문제 1](#문제 1)
3. [문제 2](#문제 2)
4. [문제 3](#문제 3)
5. [문제 4](#문제 4)
6. [문제 5](#문제 5)
## vimgolf란
타수를 줄여야 하는 골프처럼, Vim을 이용하여 여러 문제들의 적은 키보드 타수 기록에 도전하는 곳이다.
### 설치 방법
```sudo apt update```

![install_0](https://user-images.githubusercontent.com/94627358/144376833-752349c8-da35-4696-8539-91a2b8214feb.PNG)
---
```sudo apt install python```

![install_1](https://user-images.githubusercontent.com/94627358/144376837-d2a4f60a-eec1-47cc-b330-ba1cdf81ae2f.PNG)
---
```sudo apt install python3-pip```

![install_2](https://user-images.githubusercontent.com/94627358/144376839-ab2c38fa-73a7-460e-a1c8-bf47c4727b43.PNG)
---
```sudo pip install vimgolf```

![install_4](https://user-images.githubusercontent.com/94627358/144376840-84b9edf7-ea15-4bed-9717-e952b562574f.PNG)
---
### vimgolf의 실행 방법
**vimgolf의 문제 리스트 확인**

```$vimgolf list```

![list](https://user-images.githubusercontent.com/94627358/144377425-47186a1e-33c3-4dfc-b2a6-50f9ee758aa1.PNG)
**vimgolf 문제 참여 방법**

```$vimgolf put <problem hash ID>(or number)```

![1](https://user-images.githubusercontent.com/94627358/144378196-552d4c5a-231e-4aeb-ad47-75829ad59587.PNG)

## 문제 1
```GWi"<End>"<Esc>ZZ```

```G 명령어를 사용하여 맨 아래로 내려간 후에 W를 사용하여 {앞에 커서를 이동하고 i로 입력모드 전환 후 "를 입력 후 End명령어로 마지막으로 이동하여 "를 입력해준다. 그 다음에 ZZ명령어로 저장 후 종료한다```
![1](https://user-images.githubusercontent.com/94627358/144412286-923167e5-b803-4c50-be14-03ccdda44f42.gif)
|명령어|내용|
|:---:|:---:|
|G|파일의 끝으로 이동합니다.(대문자로 사용해야 함)|
|W|커서를 다음 단어로 이동합니다.|
|i|커서 위치에서 입력모드로 전환합니다.|
|End|커서가 있는 줄의 마지막으로 이동합니다.|
|ZZ|저장 후 종료|

## 문제 2
```%s/sublime\|emacs/vim/g<CR>ZZ```
![2](https://user-images.githubusercontent.com/94627358/144409380-a9e2be21-bb29-45d5-8831-06e2b552ef7c.gif)

## 문제 3
```5GqaO// <C-N> TODO<Esc><Up>q@AZZ```
![3](https://user-images.githubusercontent.com/94627358/144409399-11b4e4b1-0f25-49e8-992a-d61b18305288.gif)

## 문제 4
```9wiabs(<Right><Right>)<Esc>qaYp<C-A>w<C-A>14w<C-A>q2@Aj3dd12wrg<Up>rr<Up>rb<Esc>ZZ```
![4](https://user-images.githubusercontent.com/94627358/144409415-296709fa-4195-41c1-8ab8-9aad173e338b.gif)

## 문제 5
```Gbas<C-N><C-N>,n<C-N>,a<C-N>,sc<C-N><Esc>ZZ```
![5](https://user-images.githubusercontent.com/94627358/144409462-890ee5ac-afb1-45bc-869c-98c4ed631c5b.gif)

