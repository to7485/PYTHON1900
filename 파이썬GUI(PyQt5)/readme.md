# GUI
- 그래픽 유저 인터페이스(graphical user interface)는 사용자가 편리하게 사용할 수 있도록 입출력 등의 기능을 알기 쉬운 아이콘등의 그래픽으로 나타낸것이다.

# Qt 프레임워크
- Qt는 컴퓨터 프로그래밍에서 GUI 프로그램 개발에 널리 쓰이는 크로스 플랫폼 프레임워크이다. 
- 서버용 콘솔과 명령 줄 도구와 같은 비GUI 프로그램 개발에도 사용된다.
- 그래픽 사용자 인터페이스를 사용하는 경우에는 Qt를 위젯 툴킷으로 분류한다.
- Qt는 C++를 주로 사용하지만, 파이썬, 루비, C, 펄, 파스칼과도 연동된다.
- 수많은 플랫폼에서 동작하며, 상당히 좋은 국제화를 지원한다.
- SQL 데이터베이스 접근, XML 처리, 스레드 관리, 단일 크로스 플랫폼 파일 관리 API를 제공한다.
# PyQt5
- PyQt5는 Qt5 어플리케이션 프레임워크에 대한 파이썬 버전이다.
- P1000여 개의 클래스들을 포함하는 파이썬 모듈의 모음입니다.
- PyQt5는 윈도우, 리눅스, macOS, 안드로이드, iOS를 지원합니다.
- 아나콘다를 통해 기본적으로 같이 설치가 되어있다.

## 창 띄우기
- 창의 오른쪽 위 (Windows) 또는 왼쪽 위 (macOS)에 기본적으로 제공되는 버튼들로 창의 크기를 최대화, 최소화하거나 종료할 수 있습니다.
- 또한 마우스를 가지고 창을 이동하거나 창의 크기를 조절할 수 있습니다.
- 이러한 기능은 사실 많은 코드를 필요로 하지만 대부분의 어플리케이션에서 자주 사용되는 기능이기 때문에 이미 누군가가 코드로 만들어 놓았습니다.

```py
import sys
from PyQt5.QtWidgets import QApplication, QWidget
#필요한 모듈들을 불러옵니다. 기본적인 UI 구성요소를 제공하는 위젯 (클래스)들은 PyQt5.QtWidgets 모듈에 포함되어 있습니다.

class MyApp(QWidget):
    
    def __init__(self):
        super().__init__()
        self.initUI()
        
    def initUI(self):
        self.setWindowTitle('My First Application')
        self.move(300,300)
        self.resize(400,200)
        self.show()
        '''
        여기서 self는 MyApp 객체를 말합니다.
        setWindowTitle() 메서드는 타이틀바에 나타나는 창의 제목을 설정합니다.
        move() 메서드는 위젯을 스크린의 x=300px, y=300px의 위치로 이동시킵니다.
        resize() 메서드는 위젯의 크기를 너비 400px, 높이 200px로 조절합니다.
        show() 메서드는 위젯을 스크린에 보여줍니다.
        '''

if __name__ == '__main__':
    app = QApplication(sys.argv) #모든 PyQt5 어플리케이션은 어플리케이션 객체를 생성해야 합니다.
    ex = MyApp()
    sys.exit(app.exec_())
    '''
    '__name__'은 현재 모듈의 이름이 저장되는 내장 변수입니다.
    만약 'moduleA.py'라는 코드를 import해서 예제 코드를 수행하면 __name__ 은 'moduleA'가 됩니다.
    그렇지 않고 코드를 직접 실행한다면 __name__ 은 __main__ 이 됩니다. 
    따라서 이 한 줄의 코드를 통해 프로그램이 직접 실행되는지 혹은 모듈을 통해 실행되는지를 확인합니다.
    '''   
```

![image](https://github.com/to7485/PYTHON1900/assets/54658614/2f8f41c5-4711-4ecf-ae41-74c3a0c93aa3)

## 어플리케이션 아이콘 넣기
- 어플리케이션 아이콘은 타이틀바의 왼쪽 끝에 보여질 작은 이미지입니다. 어플리케이션 아이콘을 표시하는 방법을 소개합니다.
- 우선 폴더 안에, 아래와 같이 아이콘으로 사용할 이미지 파일을 저장해 둡니다.

```py
import sys
from PyQt5.QtWidgets import QApplication, QWidget
from PyQt5.QtGui import QIcon


class MyApp(QWidget):
    
    def __init__(self):
        super().__init__()
        self.initUI()
        
    def initUI(self):
        self.setWindowTitle('Icon')
        self.setWindowIcon(QIcon('web.png'))
        #setWindowIcon() 메서드는 어플리케이션 아이콘을 설정하도록 합니다.
        #이를 위해서 QIcon 객체를 생성하였습니다. QIcon()에 보여질 이미지('web.png')를 입력합니다.
        #이미지 파일을 다른 폴더에 따로 저장해 둔 경우에는 경로까지 함께 입력해주면 됩니다.
        self.setGeometry(300,300,300,200)
        #setGeometry() 메서드는 창의 위치와 크기를 설정합니다.
        #앞의 두 매개변수는 창의 x, y 위치를 결정하고, 뒤의 두 매개변수는 각각 창의 너비와 높이를 결정합니다.
        #이 메서드는 창 띄우기 예제에서 사용했던 move()와 resize() 메서드를 하나로 합쳐놓은 것과 같습니다.
        self.show()

if __name__ == '__main__':
    app = QApplication(sys.argv) #모든 PyQt5 어플리케이션은 어플리케이션 객체를 생성해야 합니다.
    ex = MyApp()
    sys.exit(app.exec_())
```

![image](https://github.com/to7485/PYTHON1900/assets/54658614/2c4b65e6-798a-4100-b332-ddf8a65db6b4)

# 위젯
- 위젯은 어플리케이션을 이루는 기본적인 구성 요소입니다.
- PyQt 툴킷은 간단하게 사용할 수 있는 다양한 위젯을 제공합니다.

## QPushButton
![image](https://github.com/to7485/PYTHON1900/assets/54658614/58bc95db-9378-475a-8bbc-bad8373a8e7b)

![image](https://github.com/to7485/PYTHON1900/assets/54658614/06c65e5f-b86b-404f-889c-52375140b4bf)

- 푸시 버튼(push button) 또는 명령 버튼(command button)은 사용자가 프로그램에 명령을 내려서 어떤 동작을 하도록 할 때 사용되는 버튼이다.
- GUI 프로그래밍에서 가장 흔하게 사용되고 중요한 위젯이다.

## 자주 쓰이는 메서드
|메서드|설명|
|----|----|
|setCheckable()|True설정 시, 누른 상태와 그렇지 않은 상태를 구분한다.|
|toggle()|상태를 바꾼다|
|setIcon()|버튼의 아이콘을 설정한다.|
|setEnable()|False설정 시, 버튼을 사용할 수 없다.|
|isChecked()|버튼의 선택 여부를 반환한다.
|setText()|버튼에 표시될 텍스트를 설정한다.|
|text()|버튼에 표시된 텍스트를 반환한다.|

## 자주 쓰이는 시그널
|시그널|설명|
|----|----|
|clicked()|버튼을 클릭할 때 발생한다.|
|pressed()|버튼이 눌렸을 때 발생한다.|
|released()|버튼을 눌렀다 뗄 때 발생한다.|
|toggled()|버튼의 상태가 바뀔 때 발생한다.|

```py
## Ex 5-1. QPushButton.

import sys
from PyQt5.QtWidgets import QApplication, QWidget, QPushButton, QVBoxLayout


class MyApp(QWidget):

    def __init__(self):
        super().__init__()
        self.initUI()

    def initUI(self):
        btn1 = QPushButton('&Button1', self)
        btn1.setCheckable(True)#setCheckable()을 True로 설정해주면, 선택되거나 선택되지 않은 상태를 유지할 수 있게 됩니다.
        btn1.toggle()#toggle() 메서드를 호출하면 버튼의 상태가 바뀌게 됩니다. 따라서 이 버튼은 프로그램이 시작될 때 선택되어 있습니다.
        #QPushButton 클래스로 푸시 버튼을 하나 만듭니다.
        #첫 번째 파라미터로는 버튼에 나타날 텍스트, 두 번째는 버튼이 속할 부모 클래스를 지정해줍니다.

        btn2 = QPushButton(self)
        btn2.setText('Button&2')#setText() 메서드로도 버튼에 표시될 텍스트를 지정할 수 있습니다.

        btn3 = QPushButton('Button3', self)
        btn3.setEnabled(False)#setEnabled()를 False로 설정하면, 버튼을 사용할 수 없게 됩니다.

        vbox = QVBoxLayout()
        vbox.addWidget(btn1)
        vbox.addWidget(btn2)
        vbox.addWidget(btn3)

        self.setLayout(vbox)
        self.setWindowTitle('QPushButton')
        self.setGeometry(300, 300, 300, 200)
        self.show()


if __name__ == '__main__':
    app = QApplication(sys.argv)
    ex = MyApp()
    sys.exit(app.exec_())

```

![image](https://github.com/to7485/PYTHON1900/assets/54658614/062a972d-2ac0-4ccf-8129-e63756fe223d)

##QLabel
- QLabel 위젯은 텍스트 또는 이미지 라벨을 만들 때 쓰입니다. 사용자와 어떤 상호작용을 제공하지는 않는다.
- 라벨은 기본적으로 수평 방향으로는 왼쪽, 수직 방향으로는 가운데 정렬이지만 setAlignment() 메서드를 통해 조절할 수 있다.

```py
## Ex 5-2. QLabel.

import sys
from PyQt5.QtWidgets import QApplication, QWidget, QLabel, QVBoxLayout
from PyQt5.QtCore import Qt


class MyApp(QWidget):

    def __init__(self):
        super().__init__()
        self.initUI()

    def initUI(self):
        label1 = QLabel('First Label', self) #생성자에 라벨 텍스트와 부모 위젯을 입력해줍니다.
        label1.setAlignment(Qt.AlignCenter)
        #setAlignment() 메서드로 라벨의 배치를 설정할 수 있습니다.
        #Qt.AlignCenter로 설정해주면 수평, 수직 방향 모두 가운데 위치하게 됩니다.

        label2 = QLabel('Second Label', self)
        label2.setAlignment(Qt.AlignVCenter)
        #수평 방향으로 가운데로 설정하려면 Qt.AlignHCenter를 입력해주면 됩니다.

        font1 = label1.font()
        font1.setPointSize(20)
        #라벨에 사용될 폰트를 하나 만들었습니다.
        #setPointSize() 메서드로 폰트의 크기를 설정해줍니다.

        font2 = label2.font()
        font2.setFamily('Times New Roman')
        #setFamily() 메서드로 폰트의 종류를 'Times New Roman'으로 설정해줍니다.
        font2.setBold(True)
        #setBold(True)로 폰트를 진하게 설정합니다.


        label1.setFont(font1)
        label2.setFont(font2)

        layout = QVBoxLayout()
        layout.addWidget(label1)
        layout.addWidget(label2)

        self.setLayout(layout)

        self.setWindowTitle('QLabel')
        self.setGeometry(300, 300, 300, 200)
        self.show()


if __name__ == '__main__':
    app = QApplication(sys.argv)
    ex = MyApp()
    sys.exit(app.exec_())

```

![image](https://github.com/to7485/PYTHON1900/assets/54658614/aa21b2fb-03af-45a1-b33d-ce9bd77a4110)

## 레이아웃(Layout)
- 레이아웃 (Layout)은 어플리케이션 창에 위젯들을 배치하는 방식이다.
- 레이아웃 관리는 GUI 프로그래밍에서 매우 중요한 요소이다.
- PyQt5의 위젯들을 배치하는 방식에는 절대적 배치, 박스 레이아웃, 그리드 레이아웃 방식이 있다.

### 절대적 배치
- 절대적 배치(Absolute positioning) 방식은 각 위젯의 위치와 크기를 픽셀 단위로 설정해서 배치합니다.
- 절대 배치 방식을 사용할 때는 다음의 제약을 이해하고 있어야 한다.
    - 창의 크기를 조절해도 위젯의 크기와 위치는 변하지 않는다.
    - 다양한 플랫폼에서 어플리케이션이 다르게 보일 수 있다.
    - 어플리케이션의 폰트를 바꾸면 레이아웃이 망가질 수 있다.
    - 레이아웃을 바꾸고 싶다면 완전히 새로 고쳐야 하며, 매우 번거롭다.
 
```py
## Ex 4-1. 절대적 배치.

import sys
from PyQt5.QtWidgets import QApplication, QWidget, QLabel, QPushButton


class MyApp(QWidget):

    def __init__(self):
        super().__init__()
        self.initUI()

    def initUI(self):
        label1 = QLabel('Label1', self)
        label1.move(20, 20)
        label2 = QLabel('Label2', self)
        label2.move(20, 60)

        #라벨을 만들고 x좌표,y좌표에 위치하도록 옮겨준다.

        btn1 = QPushButton('Button1', self)
        btn1.move(80, 13)
        btn2 = QPushButton('Button2', self)
        btn2.move(80, 53)

        #푸시버튼을 만들고 x,y좌표에 위치하도록 옮긴다.

        self.setWindowTitle('Absolute Positioning')
        self.setGeometry(300, 300, 400, 200)
        self.show()


if __name__ == '__main__':
    app = QApplication(sys.argv)
    ex = MyApp()
    sys.exit(app.exec_())
```

![image](https://github.com/to7485/PYTHON1900/assets/54658614/17227232-3813-4ca1-9a57-ee9f52c6a714)


### 박스 레이아웃
- 박스 레이아웃 클래스를 이용하면 훨씬 유연하고 실용적인 레이아웃을 할 수 있다.
- QHBoxLayout, QVBoxLayout은 여러 위젯을 수평으로 정렬하는 레이아웃 클래스이다.
- QHBoxLayout, QVBoxLayout 생성자는 수평, 수직의 박스를 하나 만드는데, 다른 레이아웃 박스를 넣을 수도 있고 위젯을 배치할 수도 있다.

```py
## Ex 4-2. 박스 레이아웃.

import sys
from PyQt5.QtWidgets import QApplication, QWidget, QPushButton, QHBoxLayout, QVBoxLayout


class MyApp(QWidget):

    def __init__(self):
        super().__init__()
        self.initUI()

    def initUI(self):
        okButton = QPushButton('OK')
        cancelButton = QPushButton('Cancel')
        #두 개의 버튼을 만들었다.

        hbox = QHBoxLayout()
        hbox.addStretch(1)
        hbox.addWidget(okButton)
        hbox.addWidget(cancelButton)
        hbox.addStretch(1)

        #수평 박스를 하나 만들고, 두 개의 버튼과 양 쪽에 빈 공간을 추가합니다.
        #이 addStretch() 메서드는 신축성있는 빈 공간을 제공합니다.
        #두 버튼 양쪽의 stretch factor가 1로 같기 때문에 이 두 빈 공간의 크기는 창의 크기가 변화해도 항상 같습니다.

        vbox = QVBoxLayout()
        vbox.addStretch(3)
        vbox.addLayout(hbox)
        vbox.addStretch(1)

        #다음으로 수평 박스(hbox)를 수직 박스(vbox)에 넣어줍니다.
        #수직 박스의 stretch factor는 수평 박스를 아래쪽으로 밀어내서 두 개의 버튼을 창의 아래쪽에 위치하도록 합니다.
        #이 때에도 수평 박스 위와 아래의 빈 공간의 크기는 항상 3:1을 유지합니다. stretch factor를 다양하게 바꿔보면, 의미를 잘 이해할 수 있습니다.

        self.setLayout(vbox)

        self.setWindowTitle('Box Layout')
        self.setGeometry(300, 300, 300, 200)
        self.show()


if __name__ == '__main__':
    app = QApplication(sys.argv)
    ex = MyApp()
    sys.exit(app.exec_())
```

![image](https://github.com/to7485/PYTHON1900/assets/54658614/cf4df7c6-d4e0-48f8-ba99-8257586e78ec)

### 그리드 레이아웃


## 창닫기
- 창을 닫는 가장 간단한 방법은 타이틀바의 오른쪽 (Windows) 또는 왼쪽 (macOS) 'X' 버튼을 클릭하는 것입니다.
- 이번에는 프로그래밍을 통해 창을 닫는 법을 알아보겠습니다.
- 시그널 (Signal)과 슬롯 (Slot)에 대해서도 간단하게 다뤄보겠습니다.

```py
## Ex 3-3. 창 닫기.

import sys
from PyQt5.QtWidgets import QApplication, QWidget, QPushButton
from PyQt5.QtCore import QCoreApplication
#QtCore 모듈의 QCoreApplication 클래스를 불러옵니다.


class MyApp(QWidget):

    def __init__(self):
        super().__init__()
        self.initUI()
        
    def initUI(self):
        btn = QPushButton('Quit', self)
        btn.move(50, 50)
        btn.resize(btn.sizeHint())
        '''
        푸시버튼을 하나 만듭니다.
        이 버튼 (btn)은 QPushButton 클래스의 인스턴스입니다.
        생성자 (QPushButton())의 첫 번째 파라미터에는 버튼에 표시될 텍스트를 입력하고, 두 번째 파라미터에는 버튼이 위치할 부모 위젯을 입력합니다.
        푸시버튼 위젯에 대한 자세한 설명은 QPushButton 페이지를 참고하세요.
        '''

        btn.clicked.connect(QCoreApplication.instance().quit)
        '''
        PyQt5에서의 이벤트 처리는 시그널과 슬롯 메커니즘으로 이루어집니다.
        버튼 (btn)을 클릭하면 'clicked' 시그널이 만들어집니다.
        instance() 메서드는 현재 인스턴스를 반환합니다.
        'clicked' 시그널은 어플리케이션을 종료하는 quit() 메서드에 연결됩니다.
        이렇게 발신자 (Sender)와 수신자 (Receiver), 두 객체 간에 커뮤니케이션이 이루어집니다.
        이 예제에서 발신자는 푸시버튼 (btn)이고, 수신자는 어플리케이션 객체 (app)입니다.
        '''


        self.setWindowTitle('Quit Button')
        self.setGeometry(300, 300, 300, 200)
        self.show()


if __name__ == '__main__':
    app = QApplication(sys.argv)
    ex = MyApp()
    sys.exit(app.exec_())
```

![image](https://github.com/to7485/PYTHON1900/assets/54658614/74bd748b-8f24-4987-bb1e-bce4dda30e7a)



