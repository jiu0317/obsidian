항상 뭐 설치하고 환경설정 하는게 제일 싫다.
그 중에서는 플러터는 제일 개같았다.
 D드라이브에 OS 옮기든가 해야지 빨리..

## 1
https://www.youtube.com/watch?v=mMeQhLGD-og
언제 들어도 편안해지는 영어 발음.
심신의 안정을 가져다 준다.

꼭 플러터와 다트 sdk의 환경변수 path를 추가해 주도록 하자.

## 2
위 영상을 따라해도 제대로 될 리가 없다. 
/usr/bin/env: ‘bash\r’: No such file or directory
라는 오류와 가지 각색의 오류가 뜬다. 

/usr/bin/env: ‘bash\r’: No such file or directory
는 플러터 bin 파일에 들어가서 flutter 와 dart 파일의 형식을 LF로 바꿔준다. 

환경변수 설정은 
```
nano ~/.zshrc
```
에 들어가서
```
export PATH="$PATH:$HOME/flutter/bin"
```
추가하고
```
source ~/.zshrc
```
적용하면 된다.

dos2unix 이런거 다 필요없다.