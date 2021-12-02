# 오픈소스SW개론 과제(vimgolf)
20195122_양성규
# 목차
1. [vimgolf란](#vimgolf란)
2. [Add quotes to ansible playbook](#Addquotestoansibleplaybook)
3. [simple replacements](#simplereplacements)
4. [문제 3](#Satisfythegolinter)
5. [문제 4](#Plottingsomevariablesinpython)
6. [문제 5](#Pythondataclasses)

# vimgolf란
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
## vimgolf의 실행 방법
**vimgolf의 문제 리스트 확인**

```$vimgolf list```

![list](https://user-images.githubusercontent.com/94627358/144377425-47186a1e-33c3-4dfc-b2a6-50f9ee758aa1.PNG)

**vimgolf 문제 참여 방법**

```$vimgolf put <problem hash ID>(or number)```

![1](https://user-images.githubusercontent.com/94627358/144378196-552d4c5a-231e-4aeb-ad47-75829ad59587.PNG)

# Add
- 최고점 : 8
- 나의 점수 : 9

**```GWi"<End>"<Esc>ZZ```**

```G 명령어를 사용하여 맨 아래로 내려간 후에 W를 사용하여 {앞에 커서를 이동하고 i로 입력모드 전환 후 "를 입력 후 End명령어로 마지막으로 이동하여 "를 입력해준다. 그 다음에 ZZ명령어로 저장 후 종료한다```

![1](https://user-images.githubusercontent.com/94627358/144412286-923167e5-b803-4c50-be14-03ccdda44f42.gif)
|명령어|내용|
|:---:|:---:|
|G|파일의 끝으로 이동합니다.(대문자로 사용해야 함)|
|W|커서를 다음 단어로 이동합니다.|
|i|커서 위치에서 입력모드로 전환합니다.|
|End|커서가 있는 줄의 마지막으로 이동합니다.|
|ZZ|저장 후 종료|

# simple replacements
- 최고점 : 19
- 나의 점수 : 27

**```%s/sublime\|emacs/vim/g<CR>ZZ```**

```단어를 치환해야 하는 문제이다. 우선 편집기에 들어가면 ESC를 누른 후 명령모드로 나온다.그 후 콜론을 눌러 ex모드로 진입한다. 치환을 해주는 방법은 "시작행,끝행s/원래문자열/변경문자열/옵션"이다. 그렇다면 우리는 두가지 단어를 치환을 해줘야 하기때문에 %s(전체 행을 의미)/sublime\|emacs/vim/g로 치환을 해줄 수가 있다. 옵션 g는 한 행에 '원래 문자열'에 입련한 패턴이 여러번 나오면 전체를 변경해주는 옵션이다. 이렇게 치환을 마치면 ZZ명령어를 사용하여 저장 후 종료한다.```

![2](https://user-images.githubusercontent.com/94627358/144409380-a9e2be21-bb29-45d5-8831-06e2b552ef7c.gif)
|명령어|내용|
|:---:|:---:|
|:s/old/new|현재 행의 처음 old를 new로 변경|
|:s/old/new/g|현재 행의 모든 old를 new로 변경|
|:10,20s/old/new/g|10번째 행부터 20번째 행까지 모든 old를 new로 교체|
|:-3,+4s/old/new/g|현재 커서 위치에서 3행 위부터 4행 아래까지 old를 new로 교체|
|:%s/old/new/g|문서 전체에서 old를 new로 교체|
|:%s/old/new/gc|문서 전체에서 old를 new로 확인하며 교체|
|:g/pattern/s/old/new/g|pattern이 있는 모든 행의 old를 new로 교체|

# Satisfy the go linter
- 최고점 : 20
- 나의 점수 : 21

**```5GqaO// <C-N> TODO<Esc><Up>q@AZZ```**

```새로운 행에 삽입을 해야하는 문제이다. 삽입을 2번해야하기 때문에 매크로를 사용하면 조금 더 쉬워진다. 우선 "Debug bool"문자열이 있는 행으로 이동한다. 이동한 후 매크로 저장을 위해 q+a(매크로 이름 다른거로 해도 상관 X)를 실행한다. 위에 행에 삽입할 수 있는 입력모드 전환 명령어 O를 사용하여 입력을 할 수 있게 한다. 여기서 Ctrl+n을 입력하면 자동완성 기능을 사용할 수가 있다. 그렇게 된다면 입력횟수를 줄일 수가 있다. 입력 후 위에 행으로 이동 후 매크로 저장을 끝낸다. 저장된 매크로 a를 실행할려면 @a를 입력해주면 된다. 실행을 하게 되면 "Version string"문자열 위에 "// Version TODO" 문자열이 생길 것이다. 그 후 ZZ명령어를 사용하여 저장 후 종료한다.```

![3](https://user-images.githubusercontent.com/94627358/144409399-11b4e4b1-0f25-49e8-992a-d61b18305288.gif)
|명령어|내용|
|:---:|:---:|
|5G|G명령어는 맨 아래로 내려가는 명령어이다. 여기서 5G를 해준다면 5번째 줄로 이동하게 된다.|
|q[name]|매크로를 기록하는 명령어이다.|
|O|현재 커서 위에 행을 만들고 입력모드로 전환한다.|
|<Ctrl>+n|자동완성 기능이다.|
|@a|저장된 a매크로를 실행한다.|
|ZZ|저장 후 종료|
  
# Plotting some variables in python
- 최고점 : 34
- 나의 점수 : 44
  
**```9wiabs(<Right><Right>)<Esc>qaYp<C-A>w<C-A>14w<C-A>q2@Aj3dd12wrg<Up>rr<Up>rb<Esc>ZZ```**

 ```기존에 있던 문자들을 바꿔줘야한다. 횟수 상관없이 한다면 커서를 이동하면서 바꾸면 그만이다. 하지만 우리는 횟수를 줄여야 하기때문에 방법을 찾아야 한다. 저는 2번째 행에 있는 문자열을 먼저 치환하였다. 기존 y1을 abs(y1)로 바꿔야하는데 y1이 위치한 9번째 단어로 바로 이동하여 입력모드 전환 후 새로 입력해주었다. 그 후 매크로를 실행하여 커서가 있는 줄을 복사하고 밑에 붙여넣기를 해주었다. 그 후 첫번째 숫자 x1을 증가시켜줘야하는데 Ctrl+a는 숫자를 증가 시켜주는 명령어이다. 그렇게 단어단위로 이동을 해주면서 숫자를 증가시켜준 후 매크로를 저장하고 2번연속 실행을 시켜주면 숫자는 증가를 하게 된다.매크로를 실행하면 기존에 있던 문자열들이 남아있는데 그것은 삭제를 해주면 된다. 마지막으로 color는 일일이 찾아가서 r(문자하나만 다시입력)명령어를 사용하여 바꿔준다. 그 후 ZZ명령어를 사용하여 저장 후 종료한다.```
  
![4](https://user-images.githubusercontent.com/94627358/144409415-296709fa-4195-41c1-8ab8-9aad173e338b.gif)
|명령어|내용|
|:---:|:---:|
|9w|9번째 단어로 이동한다.|
|i|현재커서에서 입력모드로 전환한다.|
|q[name]|매크로를 기록하는 명령어이다.|
|Y|현재 행을 복사한다.|
|p|밑에 내용을 붙인다.|
|<Ctrl>+a|숫자를 증가시킨다.|
|2@a|a매크로를 2번 실행한다.|
|r|한 글자만 변경한다.|
|ZZ|저장 후 종료|
  
# Python dataclasses
- 최고점 : 19
- 나의 점수 : 19
**```Gbas<C-N><C-N>,n<C-N>,a<C-N>,sc<C-N><Esc>ZZ```**

```마지막 행에 문자열을 삽입해주는 문제이다. 이 문제역시 자동완성기능을 사용하면 횟수를 줄일 수가 있다. 우선 G를 사용하여 맨아래로 이동한다. 이동한 후 b명령어를 사용하여 이전 단어의 첫 글자로 이동한다. a명령어는 현재커서 뒤에서 입력모드로 전환해준다. 그렇게 하면 ""사이에 들어가게 된다. 이제 문자열을 입력해주어야 하는데 그냥 자동완성을 하게 되면 너무 많은 문자들이 있어서 횟수가 더 늘거나게 된다. 앞에 한글자면 입력후 자동완성을 해준다면 자동완성 목록이 줄게된다. 그렇게 하나씩 입력을 해준 후 ZZ를 사용하여 저장 후 종료한다.```
  
![5](https://user-images.githubusercontent.com/94627358/144409462-890ee5ac-afb1-45bc-869c-98c4ed631c5b.gif)
|명령어|내용|
|:---:|:---:|
|G|맨 아래로 이동|
|b|이전 단어의 첫 글자로 이동|
|a|현재 커서 뒤에 입력모드 전환|
|<Ctrl>+n|자동완성 기능|
|ZZ|저장 후 
