
**总体：**


```C++
qmlRegisterType<iss::controllers::MasterController>("ISS", 1, 0, "MasterController");

iss::controllers::MasterController masterController;

QQmlApplicationEngine engine;
engine.addImportPath("qrc:/");
engine.rootContext()->setContextProperty("masterController", &masterController);

engine.load(QUrl(QStringLiteral("qrc:/views/MasterView.qml")));
```

|             类名             |           文件            | 类型  |                  作用                  |
| :------------------------: | :---------------------: | :-: | :----------------------------------: |
|   ***MasterController***   |   master-controller.h   | 总控  | 整个后端的唯一入口。持有所有子控制器和数据模型，直接对接 QML 界面。 |
| ***NavigationController*** | navigation-controller.h | 导航  |     管理页面跳转。只发送信号（Signals），不处理业务。     |
|  ***CommandController***   |  command-controller.h   | 交互  |              处理复杂的用户交互               |
|  ***DatabaseController***  |  database-controller.h  | 数据  |           封装 SQLite 数据库操作。           |

```C++
Q_PROPERTY( iss::controllers::NavigationController *ui_navigationController READ
			navigationController CONSTANT )
```


**MasterController**

|      QML Property      |       类型       |      READ       | 描述  |
| :--------------------: | :------------: | :-------------: | :-: |
|   ***ui_loginUser***   |     User*      |   loginUser()   |     |
|    ***ui_newUser***    |     User*      |    newUser()    |     |
|  ***ui_userSearch***   |  UserSearch*   |  userSearch()   |     |
| ***ui_teacherSearch*** | TeacherSearch* | teacherSearch() |     |
|  ***ui_examSearch***   |  ExamSearch*   |  examSearch()   |     |
|  ***ui_queueModel***   | JsonListModel* |  queueModel()   |     |



