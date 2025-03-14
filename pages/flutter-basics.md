# Flutter/Dart 基础语法卡片

## Dart 语言基础

### 变量与类型

```dart
// 变量声明
var name = 'Bob';      // 自动类型推断
String name = 'Bob';   // 显式指定类型
final name = 'Bob';    // 不可修改（运行时常量）
const name = 'Bob';    // 编译时常量

// 基本数据类型
int age = 20;          // 整数
double price = 9.99;   // 浮点数
bool isValid = true;   // 布尔值
String text = 'Hello'; // 字符串
```

### 集合类型

```dart
// 列表(List)
var fruits = ['Apple', 'Banana', 'Orange'];
List<String> fruits = ['Apple', 'Banana', 'Orange'];

// 映射(Map)
var person = {
  'name': 'Alice',
  'age': 25,
};
Map<String, dynamic> person = {'name': 'Alice', 'age': 25};

// 集合(Set)
var uniqueNumbers = {1, 2, 3, 4, 5};
Set<int> uniqueNumbers = {1, 2, 3, 4, 5};
```

### 函数

```dart
// 基本函数
int add(int a, int b) {
  return a + b;
}

// 箭头函数（单行函数）
int add(int a, int b) => a + b;

// 可选参数
void greet(String name, [String greeting = 'Hello']) {
  print('$greeting, $name!');
}

// 命名参数
void createUser({required String name, int age = 18}) {
  print('Creating user $name, age: $age');
}
// 调用: createUser(name: 'Alice', age: 25);
```

### 控制流程

```dart
// if条件
if (score >= 90) {
  print('优秀');
} else if (score >= 60) {
  print('合格');
} else {
  print('不合格');
}

// for循环
for (var i = 0; i < 5; i++) {
  print(i);
}

// for-in循环
for (var item in items) {
  print(item);
}

// while循环
while (condition) {
  // 代码块
}

// switch语句
switch (day) {
  case 'Monday':
    print('星期一');
    break;
  case 'Tuesday':
    print('星期二');
    break;
  default:
    print('其他日子');
}
```

### 类与对象

```dart
class Person {
  // 属性
  String name;
  int age;
  
  // 构造函数
  Person(this.name, this.age);
  
  // 命名构造函数
  Person.guest() {
    name = 'Guest';
    age = 0;
  }
  
  // 方法
  void introduce() {
    print('我是 $name, 今年 $age 岁');
  }
}

// 使用类
var person = Person('张三', 25);
person.introduce();

var guest = Person.guest();
guest.introduce();
```

## Flutter 常用组件

### 基础布局

```dart
// 垂直布局
Column(
  children: [
    Text('第一行'),
    Text('第二行'),
  ],
)

// 水平布局
Row(
  children: [
    Text('左侧'),
    Text('右侧'),
  ],
)

// 弹性布局
Expanded(
  child: Container(color: Colors.blue),
)

// 堆叠布局
Stack(
  children: [
    Container(color: Colors.grey),
    Positioned(
      top: 10,
      left: 10,
      child: Text('叠加内容'),
    ),
  ],
)
```

### 常用UI组件

```dart
// 文本
Text(
  '这是一段文本',
  style: TextStyle(
    fontSize: 16,
    fontWeight: FontWeight.bold,
    color: Colors.black,
  ),
)

// 按钮
ElevatedButton(
  onPressed: () {
    // 按钮点击事件
  },
  child: Text('点击我'),
)

// 图片
Image.asset('assets/images/logo.png')

// 输入框
TextField(
  decoration: InputDecoration(
    labelText: '用户名',
    hintText: '请输入用户名',
  ),
  onChanged: (value) {
    // 文本变化时触发
  },
)

// 列表
ListView.builder(
  itemCount: items.length,
  itemBuilder: (context, index) {
    return ListTile(
      title: Text(items[index]),
    );
  },
)
```

### 导航与路由

```dart
// 页面跳转
Navigator.push(
  context,
  MaterialPageRoute(builder: (context) => SecondPage()),
);

// 返回上一页
Navigator.pop(context);

// 替换当前页面
Navigator.pushReplacement(
  context,
  MaterialPageRoute(builder: (context) => HomePage()),
);

// 传递参数
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (context) => DetailPage(id: 123),
  ),
);
```

### 状态管理 (Provider)

```dart
// 定义数据模型
class CounterModel extends ChangeNotifier {
  int _count = 0;
  int get count => _count;
  
  void increment() {
    _count++;
    notifyListeners();
  }
}

// 在顶层提供
void main() {
  runApp(
    ChangeNotifierProvider(
      create: (context) => CounterModel(),
      child: MyApp(),
    ),
  );
}

// 在UI中使用
Consumer<CounterModel>(
  builder: (context, counter, child) {
    return Text('计数: ${counter.count}');
  },
)

// 在UI中修改
ElevatedButton(
  onPressed: () {
    Provider.of<CounterModel>(context, listen: false).increment();
  },
  child: Text('增加'),
)
```

## 石大时光圈项目常用片段

```dart
// 日历事件创建
CalendarEvent newEvent = CalendarEvent(
  title: '会议',
  notes: '项目讨论',
  startTime: DateTime.now(),
  endTime: DateTime.now().add(Duration(hours: 1)),
  reminderMinutes: [15],
  color: '#FF5733',
  id: UniqueKey().toString(),
);

// 社区帖子创建
Post newPost = Post(
  title: '二手自行车出售',
  content: '九成新山地车，价格可议',
  category: 'secondhand',
  createdAt: DateTime.now(),
  author: currentUser.id,
);
```

---

**提示**：这只是基础语法，Flutter的魅力在于组件的组合使用。加入石大时光圈项目，学以致用，才能真正掌握Flutter开发！