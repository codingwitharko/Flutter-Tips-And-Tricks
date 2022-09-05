### 100+ Flutter Tips And Tricks
 A Collection of Flutter and Dart Tips and Tricks
<div align="center">
<img src=https://github.com/aref-khodabande/Flutter-Tips-And-Tricks/blob/main/100+%20%20Flutter%20&%20Dart%20Tips.jpg?raw=true?raw=true?&style=for-the-badge&logo=github&logoColor=white alt=github style="margin-bottom: 5px;" />

<br>
<br>
<br>


### 90.`Banner` widget displays a diagonal message above the corner of another widget.


```dart
Center(
  child: Container(
    margin: const EdgeInsets.all(10.0),
    color: Colors.yellow,
    height: 100,
    child: ClipRect(
      child: Banner(
        message: "hello",
        location: BannerLocation.topEnd,
        color: Colors.red,
        child: Container(
          color: Colors.yellow,
          height: 100,
          child: Text("Hello, banner!")),
      ),),),),

```
<br>



### 89.`Baseline` is a widget that positions its child according to the child’s baseline.


```dart
Center(
  child: Container(
    color: Colors.blue,
    height: 120.0,
    width: 120.0,
    child: Baseline(
      child: Container(
        color: Colors.red,
        height: 60.0,
        width: 60.0,
      ),
      baseline: 20.0,
      baselineType: TextBaseline.alphabetic,
    ),
  ),
)

```
<br>



### 88.`LongPressDraggable` Widget is used to create a widget that can be dragged starting from LongPress.


```dart
LongPressDraggable(
  feedback: FlutterLogo(
    textColor: Colors.orange,
    size: 100,
    style: FlutterLogoStyle.stacked ),
    child: FlutterLogo(
    textColor: Colors.green,
    size: 100,
    style: FlutterLogoStyle.stacked ),
  onDragEnd: (details) { setState(() {
   final adjustment =MediaQuery.of(context).size.
   height  constraints.maxHeight;
   _offset = Offset(details.offset.dx, 
   details.offset.dy - adjustment);
    }); },)

```
<br>



### 87.`ExpansionPanel` widget is a panel with a header and a body and can be either expanded or collapsed. The body of the panel is only visible when it is expanded.


```dart
ExpansionPanel(
  isExpanded: _expanded,
  canTapOnHeader: true,
  headerBuilder: (context, isExpanded) => ListTile(
    title: Text('Click To Expand'),
  ),
  body: ListTile(
    title: Text('Description text'),
  ),
);

```
<br>



### 86.`ActionChip` widget used to create compact elements called chips, which trigger an action when the user presses on it.


```dart
ActionChip(
label: Text('Delete'),
onPressed: () =>
    print('Processing to delete item'),
);

```
<br>



### 85.`Stepper` widget displays progress through a sequence of steps.


```dart
Stepper(
  steps: [
    Step(
      isActive: true,
      state: StepState.editing,
      title: const Text('Login Info'),
      content: Column(children: <Widget>[
        TextFormField(
          decoration: InputDecoration(
          labelText: 'Email Address')),
        TextFormField(
          decoration: InputDecoration(
          labelText: 'Password')),
      ]),
    ),
  ],
);

```
<br>



### 84.`TimePicker` widget shows a dialog containing a material design time picker.


```dart
Future<TimeOfDay?> selectedTime = showTimePicker(
   context: ctx, 
   initialTime: TimeOfDay.now(),
);

```
<br>



### 83.`VerticalDivider` widget is a one device pixel thick vertical line, with padding on either side.


```dart
Row(
  mainAxisSize: MainAxisSize.min,
  children: <Widget>[
    Text('Item1') ,
    VerticalDivider(),
    Text('Item2'),
    VerticalDivider(),
    Text('Item3') 
  ])

```
<br>



### 82.`Transform` is a widget that applies a transformation before painting its child.


```dart
Container(
  color: Colors.black,
  child: Transform(
    alignment: Alignment.topRight,
    transform: Matrix4.skewY(0.3)
   ..rotateZ(-math.pi / 12.0),
    child: Container(
      padding: const EdgeInsets.all(8.0),
      color: const Color(0xFFE8581C),
      child: const Text('Apartment for rent!'),
    ),
  ),
)

```
<br>



### 81.`SelectableText` Widget allows the user to Select/Copy the content on the UI.


```dart
const SelectableText(
  'Hello! How are you?',
  textAlign: TextAlign.center,
  style: TextStyle(fontWeight: FontWeight.bold),
);

```
<br>



### 80.`Tooltip` widget helps explain the function of a button or other user interface action.


```dart
Tooltip(
  message: 'I am a Tooltip',
  child: Text('Hover over the text to show 
   a tooltip.'),
);

```
<br>



### 79.`Switch` widget is used to toggle the on/off state of a single setting.


```dart
Switch(
  value: isSwitched,
  onChanged: (value)=>
    setState(() {
      isSwitched = value;
      print(isSwitched);
    }),
  activeTrackColor: Colors.lightGreenAccent,
  activeColor: Colors.green,
),

```
<br>



### 78.`RangeSlider` widget is used to select a range from a range of values.


```dart
RangeSlider(
  values: _currentRangeValues,
  min: 0,
  max: 100,
  divisions: 5,
  labels: RangeLabels(
 _currentRangeValues.start.round().toString(),
  _currentRangeValues.end.round().toString(),
  ),
  onChanged: (RangeValues values) =>
    setState(() {  _currentRangeValues = values;
    }),
);

```
<br>



### 77.`RadioListTile` widget is a radio button with a label.


```dart
RadioListTile<SingingCharacter>(
  title: const Text('Thomas Jefferson'),
  value: SingingCharacter.jefferson,
  groupValue: _character,
  onChanged: (SingingCharacter value)=> 
  setState(() { _character = value; }),
),

```
<br>



### 76.`PhysicalModel` widget allows you to add custom shadow effects and customize its color and shape


```dart
PhysicalModel(
  elevation: 6.0,
  shape: BoxShape.rectangle,
  shadowColor: Colors.black,
  color: Colors.white,
  child: Container(
    height: 120.0,
    width: 120.0,
    color: Colors.blue[50],
    child: FlutterLogo(size: 60 ),
  ),
)

```
<br>



### 75.`PageView` is a scrollable list that works page by page.


```dart
PageView(
  children: <Widget>[
    Container(
      color: Colors.pink,
      child: Center(
        child: Text('Page 1'),
      ),
    ),
    Container(
      color: Colors.cyan,
      child: Center(
        child: Text('Page 2'),
      ),
    ),
  ],
)

```
<br>



### 74.`LinearProgressIndicator` widget is a material design linear progress indicator.


```dart
LinearProgressIndicator(
  value: controller.value,
  semanticsLabel: 
  'Linear progress indicator',
)

```
<br>



### 73.`CheckboxListTile` is a widget that combines a checkbox and a list tile. It allows you to create a checkbox along with the title, subtitle, and icon.


```dart
  CheckboxListTile(
  value: _isChecked,
  onChanged: (bool value) {
    setState(() {
      _isChecked = value;
    });
  },
)

```
<br>



### 72.You can fix `Text Overflow` error with `Flexible Widget`


```dart
Flexible(
  child: Text(
    'Flutter Text Overflow while adding long
     text. how to wrap text in flutter ',
     style: TextStyle(fontSize: 20),
  ),
)

```
<br>



### 71.`Flow` is a widget which arranges its child widgets based on FlowDelegate



```dart
Flow(
delegate: FlowMenuDelegate(
   menuAnimation: menuAnimation),
   children:
   menuItems.map<Widget>(
   (IconData icon) =>
   flowMenuItem(icon)).toList(),
);

```
<br>



### 70.Use `Divider` widget to create a one pixel thick horizontal line, with padding on either side.


```dart
ListTile(title: Text('Item1')),
Divider(),
ListTile(title: Text('Item2')),

```
<br>



### 69.Use `DecoratedBoxTransition` to animates the different properties of `DecoratedBox`.


```dart
DecoratedBoxTransition(
  position: DecorationPosition.background,
  decoration:
  decorationTween.animate(_controller),
  child: Container(
      width: 200,
      height: 200,
      padding: EdgeInsets.all(20),
      child: FlutterLogo(),
  ),
),

```
<br>



### 68.Use `Future.delayed()` to pause program flow for a certain duration.


```dart
await Future.delayed(
const Duration(seconds: 1));

```
<br>



### 67.The `AnimatedDefaultTextStyle` will transitions the default text style over a given duration whenever the given style changes.


```dart
AnimatedDefaultTextStyle(
  duration: Duration(milliseconds: 300),
  child: Text("Flutter"),
  style: newStyle,
)

```
<br>



### 66.Use `GestureDetector` to detect gestures like tap, double Tap, press, LongPress, pan, drag, zoom etc.


```dart
Container(
  color: _color,
  height: 200.0,
  width: 200.0,
  child: GestureDetector(
    onTap: ()=>
    setState(() { _color = Colors.yellow;}),
  ),
)

```
<br>



### 65.Use `CupertinoButton` Widget to create an iOS-style button that Takes in a text or an icon that fades out and in on touch.


```dart
Container(
  child: Center(
    child: CupertinoButton(
      onPressed: () {},
      child: Text("CupertinoButton Widget"),
    ),
  ),
),
Container(
  child: Center(
    child: CupertinoButton.filled(
      onPressed: () {},
      child: Text("CupertinoButton Widget"),
    ),
  ),
),

```
<br>



### 64.Use the `CupertinoAlertDialog` to create an iOS-style widget that informs the user about situations that require acknowledgement.


```dart
CupertinoAlertDialog(
  title: Text("This is the title"),
  content: Text("This is the content"),
  actions: [
    CupertinoButton(
        child: Text('Cancel'),
        onPressed: () => Navigator.of(ctx).pop();
     ),
    CupertinoButton(
      child: Text('I agree'),
      onPressed: () {
        print('I agreed');
        Navigator.of(ctx).pop();
      },
    )
  ],
)

```
<br>



### 63.Use the `AnimatedSwitcher` widget to create animation when switching between two widgets.


```dart
AnimatedSwitcher(
  duration: const Duration(milliseconds: 500),
  transitionBuilder: (Widget child,
  Animation<double> animation) {
  return ScaleTransition(child: child, 
  scale: animation);
},
child: Text( '$_count',
    key: ValueKey<int>(_count) , style:
    Theme.of(context).textTheme.headline4,
  ),
),

```
<br>



### 62.`FractionallySizedBox` Widget is a widget that sizes its child to a fraction of the total available space.


```dart
FractionallySizedBox(
  widthFactor: 0.5,
  heightFactor: 0.25,
  child: ElevatedButton(
    onPressed: () {},
    child: Text('Click Me'),
  ),
),

```
<br>



### 61.Use the `Spacer` Widget to create spacing between widgets


```dart
Column(
  children: [
    Container(
      color: Colors.red,
      height: 50,
      width: 50,
    ),
    Spacer(),
    Container(
      color: Colors.green,
      height: 50,
      width: 50,
    ),
  ],
)

```
<br>



### 60.The `RotatedBox` Widget rotates its child by an integral number of quarter turns.




```dart
RotatedBox(
  quarterTurns: 2,
  child: Text(
    'This is a Roated Text ',
    style: TextStyle(
      fontSize: 55,
      fontWeight: FontWeight.bold,
      letterSpacing: 0,
    ),
  ),
)
```
<br>



### 59.The `BackdropFilter` Widget applies a filter to the existing painted content.



```dart
BackdropFilter(
  filter: ImageFilter.blur(
    sigmaX: 10.0,
    sigmaY: 10.0,
  ),
  child: Container(
    color: 
    Colors.black.withOpacity(0.2),
  ),
)

```
<br>



### 58.The `CupertinoContextMenu` Widget is a full-screen modal route that opens when the child is long-pressed.



```dart
CupertinoContextMenu(
  child: Container(color: Colors.red),
  actions: <Widget>[
    CupertinoContextMenuAction(
      child: const Text('Action one'),
      onPressed: () =>
      Navigator.pop(context),
    ),
  ],
)
```
<br>



### 57.The `AnimatedCrossFade` Widget cross-fades between two given children and animates itself between their sizes.


```dart
AnimatedCrossFade(
  crossFadeState: _isFirst
      ? CrossFadeState.showFirst
      : CrossFadeState.showSecond,
  duration: const Duration(seconds: 1),
  firstCurve: Curves.easeInCubic,
  secondCurve: Curves.easeInCirc,
  firstChild: 
  const FlutterLogo(style:
  FlutterLogoStyle.horizontal, size: 100.0),
  secondChild: 
  const FlutterLogo(style:
  FlutterLogoStyle.stacked, size: 100.0),
)

```
<br>



### 56.The `FadeTransition` Widget fades a widget in and out by animating its opacity



```dart
FadeTransition(
       opacity: _animation,
       child: const Padding(
       padding: EdgeInsets.all(8),
       child: FlutterLogo(),
   ),
)

```
<br>



### 55.The `SlideTransition` Widget animates the position of a widget relative to its normal position.



```dart
SlideTransition(
  position: _offsetAnimation,
  child: const Padding(
    padding: EdgeInsets.all(8.0),
    child: FlutterLogo(size: 150.0),
  ),
)
```
<br>



### 54.`AnimatedOpacity` Widget automatically transitions the child’s opacity over a duration whenever the opacity changes.



```dart
AnimatedOpacity(
  opacity: _opacity,
  duration: const Duration(seconds: 1),
  curve: Curves.bounceInOut,
  // The green box must be a child of the
  AnimatedOpacity widget.
  child: Container(
    width: 200.0,
    height: 200.0,
    color: Colors.green,
  ),
)

```
<br>



### 53.The `SliverAppBar` is a widget that gives a floating app bar.


```dart
SliverAppBar(
  pinned: _pinned,
  snap: _snap,
  floating: _floating,
  expandedHeight: 160.0,
  flexibleSpace: 
  const FlexibleSpaceBar(
    title: Text('SliverAppBar'),
    background: FlutterLogo(),
  ),
)
![image](https://user-images.githubusercontent.com/37276850/186138909-25ee40f5-45a8-401e-9443-09ddadf37df3.png)

```
<br>



### 52.The `AnimatedContainer` widget is a container widget with animations. It can be animated by altering the values of its properties.


```dart
AnimatedContainer(
  width: _width,
  height: _height,
  decoration: BoxDecoration(
    color: _color,
    borderRadius: _borderRadius,
  ),
  duration: Duration(seconds: 1),
  curve: Curves.fastOutSlowIn,
)

```
<br>




### 51.The `wrap` is a widget that displays its children in horizontal or vertical runs. 
It will try to place each child next to the previous child on the main axis. If there is not enough space, it will create a new run adjacent to its existing children in the cross axis.


```dart
Wrap(
  children: List.generate(10, 
      (index) => Container(
      margin: const EdgeInsets.all(10),
      color: Colors.green,
      height: 100,
      width: 100,
    ),
  ),
);

```
<br>



### 50.LayoutBuilder helps to create a widget tree that can depend on the size of the parent widget.


```dart
LayoutBuilder(
  builder: (context, constraints) {
    if (constraints.maxWidth >= 750) {
      return Container(
        color: Colors.green,
        height: 100,
        width: 100,
      );
    } else {
      return Container(
        color: Colors.yellow,
        height: 100,
        width: 100,
      );
    }
  },
);
```
<br>


### 49.You can create multiple shadows for a `Text widget`.


```dart
Text('Important Text',
  style: TextStyle(
    color: Colors.black,
    fontSize: 50,
    fontWeight: FontWeight.bold,
    shadows: [
      Shadow(
          color: Colors.red[500]!,
          offset: const Offset(-50, -50),
          blurRadius: 5),
      Shadow(
          color: Colors.green[200]!,
          offset: const Offset(50, 50),
          blurRadius: 5),
    ],
  ),
);

```
<br>


### 48.You can use the `ColorFiltered` widget to apply a color filter to its child widgets.

```dart
Column(
  children: [
    // The original image
    Image.network(_imageUrl),

    // The black-and-white image
    ColorFiltered(
      colorFilter: 
      const ColorFilter.mode(Colors.grey,
      BlendMode.saturation),
      child: Image.network(_imageUrl),
    ),
  ],
);

```
<br>


### 47.`AnimatedSize` is a widget that automatically transitions its size over a given duration whenever the given child’s size changes.


```dart
double _size = 50.0;
bool _large = false;

void _updateSize() {
  setState(() {
    _size = _large ? 250.0 : 100.0;
    _large = !_large; 
});
}

```
```dart

GestureDetector(
  onTap: () => _updateSize(),
  child: Container(
    color: Colors.amberAccent,
    child: AnimatedSize(
      vsync: this,
      curve: Curves.easeInCirc,
      duration: 
      const Duration(seconds: 2),
      child: FlutterLogo(size: _size),
),
),
);
```

<br>


### 46.You can use the `ShaderMask` widget to apply a `gradient` look and feel to its child.


```dart
Center(
  child: ShaderMask(
    blendMode: BlendMode.srcIn,
    shaderCallback: (Rect bounds) {
      return const LinearGradient(
        colors: [Colors.red, Colors.green],
        tileMode: TileMode.clamp,
      ).createShader(bounds); },
    child:
    const Text('This is a colorful Text',
    style:TextStyle(fontSize: 36) ,
     ),
   ),
)

```
<br>


### 45.You can create a circular icon button using `ElevatedButton`. 

```dart
ElevatedButton(
  onPressed: () {},
  style: 
  ElevatedButton.styleFrom(
      shape: CircleBorder(), 
      padding: EdgeInsets.all(30) ,
    ),
    child: Icon(
    Icons.add,
    size: 50,
  ),
)

```
<br>


### 44.Use the `barrierDismissible` property to prevent dismissing the `AlertDialog` when the user taps on the screen outside the alert box.


```dart
showDialog<String>(
  context: context,
  barrierDismissible: false,
  builder: (BuildContext context) =>
      AlertDialog(
        title: const Text('This is a title'),
        content: 
        const Text('This is a description'),
        actions: <Widget>[
          TextButton(
            onPressed: () =>
            Navigator.pop(context, 'Cancel'),
            child: const Text('Cancel'),
          ),
          TextButton(
            onPressed: () =>
            Navigator.pop(context, 'OK'),
            child: const Text('OK'),
          ),
    ], 
  ),
 );

```
<br>


### 43.You can provide an action label in `SnackBar` to act when `pressed` on it as below


```dart
final snackBar = SnackBar(
  content: 
  const Text('Amazing SnackBar!'),
  action: SnackBarAction(
    label: 'Undo',
    onPressed: () {
      // Do something.
    },
  ),
);
```
<br>


### 42.Center the FloatingActionButton by setting the floatingActionButtonLocation parameter as below


```dart
Scaffold(
  floatingActionButtonLocation:
  FloatingActionButtonLocation.centerFloat,

  floatingActionButton: 
  FloatingActionButton(
    onPressed: () {},
    child: Icon(Icons.settings_voice),
  ),

  ...

);

```
<br>


### 41.Use the `ListView` to create a `horizontal` list by setting the scrollDirection parameter to `Axis.horizontal`


```dart
ListView(
  scrollDirection: Axis.horizontal,
  children: [

    /// some object

  ],
);

```
<br>


### 40.There are `four` different ways to append or concatenate Strings
Using ‘+’ operator
```dart
String str1 = "Dart";
String str2 = "Is";
String str3 = "Fun";

print(str1 + str2 + str3);

```
String interpolation.

```dart

String str1 = "Dart";
String str2 = "Is";
String str3 = "Fun";

print('$str1 $str2 $str3');
```
Directly writing string literals.

```dart
print('Dart' 'Is' 'Fun');
```
Strings.join() method.
```dart

  // Creating List of strings
  
List<String> str = ["Dart", "Is", "Fun"];

  String _thestr = str.join();
  print(_thestr);

  _thestr = str.join(" ");
  print(_thestr);

```

<br>


### 39.`Getters` and `setters` are special methods that provide read and write access to an object’s properties.

```dart
class Rectangle {
  double left, top, width, height;
  Rectangle(this.left, this.top, this.width,this.height);
  
 double get right => left + width;
  set right(double value) => left = value - width;

  double get bottom => top + height;
  set bottom(double value) => top = value - height;
}

void main() {
  var rect = Rectangle(3, 4, 20, 15);
  print(rect.left);
  rect.right = 12;
  print(rect.left);
}

```
<br>


### 38.You can pass a function as a parameter to another function.
```dart
void main() {
  const list = ['Tehran', 'Zanjan', 'Tabriz'];
  for (var item in list) {
    if (kDebugMode) {
      print('City Of $item');
    }
  }
}
![image](https://user-images.githubusercontent.com/37276850/186124219-723774c0-66ad-480e-8287-6eeae5acefee.png)

```
<br>


### 37.Use `MediaQuery` to get information about the current device size, its orientation, and user preferences.

```dart
var orientation = 
MediaQuery.of(context).orientation;
var height = 
MediaQuery.of(context).size.height;
var width = 
MediaQuery.of(context).size.width;

return orientation == Orientation.portrait
    ? Container(
        color: Colors.green,
        height: height / 4,
        width: width / 4,
      )
    : Container(
        height: height / 3,
        width: width / 3,
        color: Colors.yellow,
      );
```
<br>


### 36.`SafeArea` is a padding widget that inserts its child with enough padding to keep it from being blocked by the system status bar, notches, holes, rounded corners, and others.


```dart
@override
Widget build(BuildContext context) {
  return  Scaffold(
    body: SafeArea(
      top: true,
      bottom: true,
      left: true,
      right: true,
      minimum: EdgeInsets.all(16.0),
      maintainBottomViewPadding: true,
      child: Text('Check this important text'),
    ),
  );
}
```
<br>


### 35.Use `FittedBox` to scale and fit the child widget inside. It restricts its child widgets from growing their size beyond a specific limit. It re-scales them according to the size available.

```dart
Center(
  child: Row(children: [
    Expanded(
      child: FittedBox(
        child: Text(
          "It is a long established fact that a "
           "reader will be distracted by the readable "
           "content of a page when looking at its layout.",
          maxLines: 1,
          style: TextStyle(fontSize: 23),
        ),
      ),
    ),
  ]),
)

```
<br>


### 34.You can have a `background color` behind a `text` and add a curve at the start and the end.


```dart
Center(
  child: Text(
    'This is a very important text ',
    style: TextStyle(
        fontWeight: FontWeight.w600,
        color: Colors.white,
        fontSize: 20,
        background: Paint()
          ..strokeWidth = 30.0
          ..color = Colors.red
          ..style = PaintingStyle.stroke
          ..strokeJoin = StrokeJoin.round),
  ),
)
![image](https://user-images.githubusercontent.com/37276850/186123675-46fdbaeb-e8b5-404f-9874-f810575cfd72.png)

```
<br>


### 33.You can use `InkWell` to create a ripple effect to produce a visual experience for touch response.

```dart
InkWell(
  splashColor: Colors.red,
  onTap: () {},
  child: Card(
    elevation: 5.0,
    child: Text(
      ' Click This ',
      style: Theme.of(context).textTheme.headline2,
    ),
  ),
);
```
<br>


### 32.`Dart` allows you to create a `callable class` so you can call the instance of the class as a `function`


```dart
class WelcomeToTheCity {
  // Defining call method
  String call(String a, String b, String c) => 
  'Welcome to $a$b$c';
}

void main() {
  var welcomeToCity = WelcomeToTheCity();

  // Calling the class through its instance
  var welcomeMsg = 
  welcomeToCity('SanDiego ', 'CA ', 'USA');

  print(welcomeMsg);
}
```
<br>


### 31.`Enums` and `extension methods` can make code cleaner to read. In the example below, we are converting Enums to Strings.

```dart
enum Cities { Tehran, Zanjan, Tabriz }

extension ToString on Cities {
  String get name => toString().split('.').last;
}

void main() {
  print(Cities.Tehran.name);
  print(Cities.Zanjan.name);
  print(Cities.Tabriz.name);
}
```
<br>


### 30.To write any Dart program, be it a script or a Flutter app, you must define a function called `main()`. It is the entry point of every app.


```dart
void main() {
  var list = ['London', 'Dublin', 'Paris'];
  for (var item in list) {
    print('${list.indexOf(item)}: $item');
  }
}
```
<br>


### 29.Set `debugShowCheckedModeBanner to false to remove the `Debug Banner Tag`


```dart
MaterialApp(
  debugShowCheckedModeBanner: false,
  // other arguments
);
```
<br>


### 28.Use the List class method `join()` can to join a List of any type to a String.


```dart
List<String> values = ['dart', 'flutter', 'fun'];
print(values.join()); //  dart,flutter,fun
![image](https://user-images.githubusercontent.com/37276850/186119951-041eaba1-0be7-473f-addb-b641a88f4cd7.png)
```
<br>


### 27.Use themes to define a set of colors, fonts, shapes, and design styles throughout your app. It’s a way to centralize all your stylistic decisions in one place.


```dart
MaterialApp(
 ...
  theme: ThemeData(
    // The default brightness and colors.
    brightness: Brightness.light,
    primaryColor: Colors.lightGreen[500],
    accentColor: Colors.amber[600],
    // The default font family.
    fontFamily: 'Georgia',
    // TextTheme & text styling
    textTheme: TextTheme(
      headline1: TextStyle(
		fontSize: 64.0, fontWeight: FontWeight.bold),
      headline6: TextStyle(
		fontSize: 36.0, fontStyle: FontStyle.italic),
      bodyText2: TextStyle(
		fontSize: 14.0, fontFamily: 'Hind'),
    ),
  ),
);

```
<br>


### 26.get access to the index on an Item in a list, you need to convert the list to a map using the `asMap`.
```dart
myList.asMap().entries.map((entry) {
  int idx = entry.key; // index
  String val = entry.value;
  return something;
}
```
<br>


### 25.Use `Stack` to `overlap` widgets, The first widget will be the bottommost item, and the last widget will be the topmost item.
```dart
Stack(
  children: [
    Container(
      width: 100,
      height: 100,
      color: Colors.red,
    ),
    Container(
      width: 90,
      height: 90,
      color: Colors.green,
    ),
    Container(
      width: 80,
      height: 80,
      color: Colors.blue,
    ),
  ],
);

```
<br>


### 24.Use the `Hero` widget to animate a widget from one screen to the next. e.g., an icon on the first page flying to the second page.
```dart
// Page 1
Hero(
  tag: "FlyingHero",
  child: Icon(
    Icons.party_mode_outlined,
    size: 50.0,
  ),
);

```
```dart
// Page 2
Hero(
  tag: "FlyingHero",
  child: Icon(
    Icons.party_mode_outlined,
    size: 150.0,
  ),
);

```
<br>


### 23.You can size the widgets to fit within a row or column using the `Expanded widget`.


```dart
Row(
  crossAxisAlignment: CrossAxisAlignment.center,
  children: [
    Expanded(
      child: Image.asset('images/pic1.jpg'),
    ),
    Expanded(
      child: Image.asset('images/pic2.jpg'),
    ),
    Expanded(
      child: Image.asset('images/pic3.jpg'),
    ),
  ],
);

```
<br>


### 22.You can use the services library to hide the `status bar`.
```dart

import 'package:flutter/services.dart';

void main(){
 
  SystemChrome.setEnabledSystemUIMode(
  SystemUiMode.manual,
  overlays: [],
  );

}
```
<br>

### 21.You can turn any color to a `Material Color`


```dart
const Map<int, Color> color = {
  50: Color.fromRGBO(255, 207, 68, .1),
  100: Color.fromRGBO(255, 207, 68, .2),
  200: Color.fromRGBO(255, 207, 68, .3),
  300: Color.fromRGBO(255, 207, 68, .4),
  400: Color.fromRGBO(255, 207, 68, .5),
  500: Color.fromRGBO(255, 207, 68, .6),
  600: Color.fromRGBO(255, 207, 68, .7),
  700: Color.fromRGBO(255, 207, 68, .8),
  800: Color.fromRGBO(255, 207, 68, .9),
  900: Color.fromRGBO(255, 207, 68, 1),
};

const MaterialColor custom_color =
MaterialColor(0xFFFFCF44, color);
```
<br>


### 20.You can use the `dart:io` library to write a `platform-specific` code


```dart
import 'dart:io' show Platform;

...


if (Platform.isIOS) {
  doSomethingforIOS();
}

if (Platform.isAndroid) {
  doSomethingforAndroid();
}

```
<br>

### 19.You can use the services library to lock the `device orientation`


```dart
import 'package:flutter/services.dart';

...

void main() async {
  await SystemChrome.setPreferredOrientations(
 [DeviceOrientation.portraitUp]);

  runApp(App());
}
```
<br>

### 18.You can randomly select an item from a list using Random from `dart:math`


```dart
import 'dart:math';

...

int min = 0;
int max = someList.length - 1;
Random rnd = new Random();
int r = min + rnd.nextInt(max - min);
return someList[r];
```
<br>

### 17. You can use `GridView.count` to create a grid that’s two tiles wide in `portrait` mode and three tiles wide in `landscape` mode

```dart
Flexible(
  child: GridView.count(
    crossAxisCount: 
    (orientation == Orientation.portrait) ? 2 : 3,
    mainAxisSpacing: 4.0,
    crossAxisSpacing: 4.0,
    padding: const EdgeInsets.all(4.0),
    childAspectRatio: 
    (orientation == Orientation.portrait) ? 1.0 : 1.3,
    children: someList.map((catData) => 
        aListItemWidget(catData)).toList(),
  ),
);
```
<br>

### 16. You can wait for the results of multiple Futures to complete using `Future.wait`

```dart
class someAPI {
  Future<int> getThings() => Future.value(3000);
  Future<int> getItems() => Future.value(300);
  Future<int> getStuff() => Future.value(30);
}
```
```dart
final api = someAPI();
final values = 
await Future.wait([
  api.getThings(),
  api.getItems(),
  api.getStuff(),
]);
```
<br>

### 15. You can iterate through a map in a null-safe manner using entries.

```dart
for (var entry in items.entries) {
  //print the keys and values
  print('${entry.key}: ${entry.value}');
}
```
<br>

### 14. Apply `HitTestBehavior.opaque` on `GestureDetector` to make the entire size of the gesture detector a hit region!


If your `GestureDetector` isn't picking up gestures in a `transparent/translucent` widget, make sure to set its behavior to `HitTestBehavior.opaque` so it'll capture those events.


```dart
GestureDetector(
  behavior: HitTestBehavior.opaque,
  onTap: () => print('Tap!'),
  child: Container(
    height: 250,
    width: 250,
    child: Center(child: Text('Gesture Test')),
  ),
)

```

You can provide Image according to your need, also you can use the box decoration properties to provide shape and border.

<br>
<br>

### 13. Check if `release mode` or not

You can use kReleaseMode constant to check if the code is running in release mode or not. kReleaseMode is a top-level constant from foundation.dart.
More specifically, this is a constant that is true if the application was compiled in Dart with the `-Ddart.vm.product=true` flag.

```dart
import 'package:flutter/foundation.dart';

print('Is Release Mode: $kReleaseMode');


```
<br>

### 12. Set `background image` to your `Container`.

Want to set the background image to your `Container?` And you are using a Stack to do so? There is a better way to achieve this result. You can use `decoration` to set the image in the `container`.


```dart
Container(
  width: double.maxFinite,
  height: double.maxFinite,
  decoration: BoxDecoration(
    image: DecorationImage(
      image: NetworkImage('https://bit.ly/2oqNqj9'),
    ),
  ),
  child: Center(
    child: Text(
      'Flutter.dev',
      style: TextStyle(color: Colors.red),
    ),
  ),
);
```
<br>

### 11. Prefer single quotes for `strings!`

Use double quotes for nested strings or (optionally) for strings that contain single quotes. For all other strings, use single quotes.!


```dart
final String name = 'Flutter And Dart Tips';

print('Hello ${name.split(" ")[0]}');
print('Hello ${name.split(" ")[2]}');

```

<br>

### 10. Implement `assert()` messages in Dart.

Do you know that you can throw your message when your assert fails? `assert()` takes an optional message in which you can pass your message.


```dart
assert(title != null, "Title string cannot be null.");
```

<br>

### 9. Having trouble displaying `splashes` using an `InkWell`?
Use an Ink widget! The Ink widget draws on the same widget that InkWell does, so the splash appears.

```dart
class InkWellCard extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Card(
      elevation: 3.0,
      child: Ink(
        child: InkWell(
          onTap: () => print("Ordering.."),
          child: Text("Order Bagels"),
        ),
      ),
    );
  }
}
```
<br>

### 8.Want to `log data` on the system `console` in Flutter?


You can use the `print()` function to view it in the system console. If your output is too much, then Android sometimes discards some log lines. To avoid this, you can use `debugPrint()`.
You can also log your print calls to disk if you're doing long-term or background work.

<br>


### 7. `Cascade` Notation - Method Chaining on Steroids


Cascades Notation (..) allows chaining a sequence of operations on the same object. Besides, fields (data-members) can be accessed using the same.

```dart
class Person {
  String name;
  int age;
  Person(this.name, this.age);
  void data() => print("$name is $age years old.");
}
```
```dart
// Without Cascade Notation
Person person = Person("Richard", 50);
person.age = 22;
person.name += " Parker";
person.data();

// Cascade Notation with Object of Person
Person("Jian", 21)
  ..age = 22
  ..name += " Yang"
  ..data();

// Cascade Notation with List
<String>["Natasha", "Steve", "Peter", "Tony"]
  ..sort()
  ..forEach((name) => print("\n$name"));
```
<br>

### 6. Want to set different Theme for a particular widget?
Just wrap the widget with the Theme Widget and pass the ThemeData().


```dart
Theme(
  data: ThemeData(...),
  child: TextFormField(
      decoration: const InputDecoration(
        icon: Icon(Icons.person),
        hintText: 'What do people call you?',
        labelText: 'Name *',
      ),
      validator: (value) {
        return value!.contains('@')? 
        'Do not use the @ char': null;
      }
  ),
)

```
<br>

### 5. Use a `Ternary` operator instead of the `if-else` to shorter your Dart code.

Instead of this.

```dart
void main() {
  bool isAndroid = true;
  getDeviceType() {
    if (isAndroid) {
      return "Android";
    } else {
      return "Other";
    }
  }
  print("Device Type: " + getDeviceType());
}
```

Use below.

```dart
void main() {
  bool isAndroid = true;
  getDeviceType() => isAndroid ? "Android" : "Other";
  print("Device Type: " + getDeviceType());
}
```
<br>

### 4. Apply style as a Theme in a `Text` widget!

```dart
Text(
  "Your Text",
  style: Theme.of(context).textTheme.title,
)
```
<br>

### 3. Do not explicitly initialize variables to `null`.


Adding = null is redundant and unneeded.

```dart
// Good
  var title;

// Bad
  var title = null;

```
<br>

### 2. Using `ListView.separated()`
Want to add the separator in your Flutter ListView?
Go for the ListView.separated();


```dart
ListView.separated(
  itemCount: Items.length,
  itemBuilder: (ctx, i) => ExampleNameItem(),
  // Separator can be any widget.
  separatorBuilder:(ctx, i) =>const Divider(),
);
```
<br>

### 1. Using `null-aware operators`
While checking the null in the Dart, Use null-aware operators help you reduce the amount of code required to work with references that are potentially null.!


```dart
// instead of
if (title == null) {
  title = "Title";
}
// User below
title ??= "Title";

```
