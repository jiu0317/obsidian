다트 복습
for flutter

+git 사용 습관 들이기..

## 컴파일

다트는 개발 도중에는 VM에서 JIT(Just In Time)으로 컴파일 한다. 
개발이 끝나고 배포를 할 때는 AOT(Ahead Of Time)으로 컴파일 한다.

## sound null safety

null값을 참조하게 되면 에러가 나는 현상(null dereference)을 컴파일 전에 잡아내기 위해 null safety 도입. 

```dart
String? name // Nullable 

String name // Non-nullable
```

```dart
  String? name = 'jiu';

  name = null;
```

```dart
  String? name = 'jiu';

  name = null;

  

  if (name != null) {

    name.isNotEmpty;

  }

  name?.isNotEmpty; / 위 if문과 같은 역할을 한다!! (name이 null이 아니라면~)
```
변수를 사용하기 전에 초기화 해야한다.

- **Nullable의 기본 값은 null이기에 null로 초기화 된다.** 
- **Non-nullable 은 초기 값을 지정하지 않는다. 사용자에게 초기화를 강제하므로.**
- **다트에서는 초기화 되지 않은 값을 가져올 수 없다.** 
- **Nullable 타입은 값에 접근하거나 메소드를 부를 수 없다.** 


dart sdk 설치 경로
The install of dart-sdk was successful.
  Deployed to 'C:\tools'


## var

```dart
var name = 'jiu';
```
name은 타입이 스트링인 다른 값으로 바꿀 수 있다. 

```dart
String name = 'jiu';
```

관습적으로 함수나 메소드 내부에 지역변수를 선언할 때는 var 사용.
클래스에서 변수나 property를 선언할 때는 타입을 지정한다. 


## dynamic

// 반드시 필요할 때만 사용하기!
```dart
var name;
//or
dynamic name;

name = 'jiu';
name = 12;
name = true;
```
--> dynamic type.

```dart
dynamic name;

if(name is String){
	//~~~~~~~
}
```


## Final Variable

var, String.. 의 타입을 사용한 변수 생성을 나중에 변수의 값을 바꿀 수 있다. 

변수값이 수정되지 못하게 하려면 'final' 사용.

```dart
final name = 'jiu';

/or

final String name = 'jiu'; 
```


## Late Variable

late는 초기 데이터 없이 변수를 선언할 수 있게 해준다. 
API 등을 통해 데이터가 생기면 나중에 변수 값을 넣는다. 

변수 나중에 초기화.
초기화 하기 전에는 값에 접근 못하게 막음.

```dart
late final name;
// Do something . . .(API)
name = 'jiu';
```

## Constant Variable

const는 compile-time constant를 만들어 준다. 

컴파일을 할 때 이미 변수의 초기값이 설정되어 있어야 한다.
```dart
const max_price = 120;
```



## Recap

int, String : 타입 지정, 수정 가능

var : 타입 미지정, 수정 가능

final : late 사용 가능(런타임 도중에 선언 가능), 수정 불가

dynamic : 타입 변경 가능, if로 타입 조사 후 사용, 수정 가능

const : 컴파일 당시 값이 있어야함(런타임 도중 선언 불가), 수정 불가

null-safety : null을 참조하지 못하게 막아줌. 모든 변수는 기본적으로 non-nullable, 타입 뒤에 ? 붙이면 null 가능
nullable은 if로 null인지 아닌지 조사 후 사용
아니면 더 짧게 (변수명?.method)으로 사용.

late : 변수의 초기화를 미룰 수 있음. 초기화 전에 사용 못함.
API 사용시 유용.
late final name;
late final String name;

## Basic Data Types

String name = 'jiu';
bool alive = true;
int age = 22;
double any = 99.9;

num x = 22;
x = 21;  --> num은 int일 수도, double일 수도 있음.

다트의 거의 모든 것이 object로 이루어져 있음.
int와 와 double은 모두 num을 상속받음.
