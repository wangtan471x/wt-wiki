### 样例参考

1. [Qt for Python之 PySide2+QML 入门示例](https://blog.csdn.net/luoyayun361/article/details/82935420)
2. [白月黑羽教Python](http://www.python3.vip/)
3. Digitser [http://pyside.digitser.net/5.15/zh-CN/PySide2/QtWidgets/QPushButton.html](http://pyside.digitser.net/5.15/zh-CN/PySide2/QtWidgets/QPushButton.html)
4. Qt论坛 [http://www.qtcn.org/bbs/i.php](http://www.qtcn.org/bbs/i.php)
5. PyQt (PySide) 与 QML 互操作 - PyQt, QML ListView, model, QAbstractListModel[https://blog.csdn.net/likianta/article/details/105820227](https://blog.csdn.net/likianta/article/details/105820227)

6. 如何将python和qml与pyside2连接起来?[http://ask.sov5.cn/q/4q5a0ekhsG](http://ask.sov5.cn/q/4q5a0ekhsG)



### Python操作qml对象

参考网站：[https://blog.csdn.net/weixin_30312557/article/details/102067204](https://blog.csdn.net/weixin_30312557/article/details/102067204)

1. 如何在python里获得qml里的对象？
  1.1 获取根对象（Python）

  使用QQmlApplicationEngine类的rootObjects方法，返回的是一个列表，取索引0即是根对象。

  ```python
  engine = QQmlApplicationEngine()
  engine.load('qml-test.qml')
  root_obj = engine.rootObjects()[0]
  ```

  这样就会获得id为window的ApplicationWindow对象。

  1.2 获取任意对象

  需要在qml文件中加入objecName属性！

  ```python
  engine = QQmlApplicationEngine()
  engine.load('qml-test.qml')
  txt_obj = engine.rootObjects()[0].findChild(QObject, "txt")
  ```

2. 如何在python里读取和设置qml对象的属性和值？

  2.1 读取对象的属性(如Text对象)
  首先通过 findChild 获取Text对象（注意 txt 是qml文件里的 objectName）：

  txt_obj = engine.rootObjects()[0].findChild(QObject, "txt")
  然后获取Text对象的text属性（使用 property）：

  txt_value = txt_obj.property("text")
  2.2 设置对象的属性
  使用setProperty方法可以更改对象的属性值。

  txt_obj.setProperty("text", "Clicked!")



1. 





