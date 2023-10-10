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


