# [CustomWidget]


## 1.1 텍스트뷰 커스터마이징


### 화면 출력

![](http://i.imgur.com/gtInKBI.png )

--> "Hello world!" 위젯 위에 텍스트뷰가 있습니다. 안드로이드에 있는 텍스트뷰를 사용하지 않고 직접 클래스로 정의하여 화면에 띄워보겠습니다.




[Today.java]

![](http://i.imgur.com/nL5wvl4.png)

(1) 먼저 사용자가 원하는 텍스트뷰를 화면에 띄우기 위해서는 클래스로 상속을 받아야 됩니다.
이때 생성자로 넘어오는 값 중, AttributeSet은 위젯의 속성값들입니다.

(2) "editText.setText("hello world");" 를 떠올리면 됩니다. setText() 메소드를 사용자가 직접 정의합니다. 여기서는 현재 날짜가 출력되도록 하였습니다.



[activity_main.xml]

![](http://i.imgur.com/CIFTc69.png)

--> TextView를 상속받은 클래스를 메모리에 올리고 나면 .xml에서 직접 가져다 사용할 수 있습니다. 여기서는 패키지명 + 클래스 이름 형태로 가져왔습니다.

## 1.2 속성 커스터마이징

### 화면 출력

![](http://i.imgur.com/aT4ehFm.png)

--> 이번에는 속성을 직접 사용자가 정의하여 현재 날짜를 출력할 때 '/'가 포함되도록 하였습니다.

### New Resource File 생성

![](http://i.imgur.com/Jbn8Gzq.png)

--> attrs 레이아웃 파일을 생성합니다.


![](http://i.imgur.com/ygWwbHO.png)

--> attribute로 사용할 속성을 정의합니다. delimeter 속성을 만듭니다.

### 코드

[Today.java]

![](http://i.imgur.com/fv6qF17.png)
![](http://i.imgur.com/1EqFXUA.png)

(1) 생성자에서는 .xml의 속성들과 attrs의 속성들을 매칭시켜서 현재 속성에 입력되어 있는 값을 가져오는 작업을 합니다.

(2) setDate()에서는 생성자에서 꺼내온 입력값( 여기서는 '/')을 실제 출력할 데이터에 적용합니다. 즉 날짜 포맷을 정의합니다.


[activity_main.xml]

![](http://i.imgur.com/djG2mGG.png)

--> 사용자가 정의한 custom 속성을 사용하기 위해서는 먼저 xmlns:custom을 선언합니다.

				xmlns:custom="http://schemas.android.com/apk/res-auto"

--> 사용자가 정의한 custom 속성을 다음과 같은 형태로 정의합니다.

				custom : 사용자 속성 = 입력값
				custom:delimeter = "/"

--------------------------------------------
