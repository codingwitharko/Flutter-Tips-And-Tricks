# 100 plus - Flutter-Tips-And-Tricks
 A Collection of Flutter and Dart Tips and Tricks

<br>
<br>
<br>
### 20.

```dart

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
![image](https://user-images.githubusercontent.com/37276850/186096907-2c4bb9a7-c26c-4551-b71b-c0f5fd05d7a4.png)
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
![image](https://user-images.githubusercontent.com/37276850/186094612-f7fb41cb-3b51-4a62-a3dd-670e3e4c0e3e.png)

```
