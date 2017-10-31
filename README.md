<p align="center">
<img alt="FromJavaToKotlin" src="https://raw.githubusercontent.com/MindorksOpenSource/from-java-to-kotlin/master/assets/from_java_to_kotlin.png">
</p>

# From Java To Kotlin
[![Mindorks](https://img.shields.io/badge/mindorks-opensource-blue.svg)](https://mindorks.com/open-source-projects)
[![Mindorks Community](https://img.shields.io/badge/join-community-blue.svg)](https://mindorks.com/join-community)
> From Java To Kotlin - Your Cheat Sheet For Java To Kotlin

[中文支持](https://github.com/MindorksOpenSource/from-java-to-kotlin/blob/master/README-ZH.md)
---

> Java

```java
System.out.print("Amit Shekhar");
System.out.println("Amit Shekhar");
```

> Kotlin

```kotlin
print("Amit Shekhar")
println("Amit Shekhar")
```

---

> Java

```java
String name = "Amit Shekhar";
final String name = "Amit Shekhar";
```

> Kotlin

```kotlin
var name = "Amit Shekhar"
val name = "Amit Shekhar"
```

---

> Java

```java
String otherName;
otherName = null;
```

> Kotlin

```kotlin
var otherName : String?
otherName = null
```

---

> Java

```java
if (text != null) {
  int length = text.length();
}
```

> Kotlin

```kotlin
text?.let {
    val length = text.length
}
// or simply
val length = text?.length
```

---

> Java

```java
String firstName = "Amit";
String lastName = "Shekhar";
String message = "My name is: " + firstName + " " + lastName;
```

> Kotlin

```kotlin
val firstName = "Amit"
val lastName = "Shekhar"
val message = "My name is: $firstName $lastName"
```

---

> Java

```java
String text = "First Line\n" +
              "Second Line\n" +
              "Third Line";
```

> Kotlin

```kotlin
val text = """
        |First Line
        |Second Line
        |Third Line
        """.trimMargin()
```

---

> Java

```java
String text = x > 5 ? "x > 5" : "x <= 5";

String message = null;
log(message != null ? message : "");
```

> Kotlin

```kotlin
val text = if (x > 5)
              "x > 5"
           else "x <= 5"

val message: String? = null
log(message ?: "")
```

---

> Java

```java
final int andResult  = a & b;
final int orResult   = a | b;
final int xorResult  = a ^ b;
final int rightShift = a >> 2;
final int leftShift  = a << 2;
```

> Kotlin

```kotlin
val andResult  = a and b
val orResult   = a or b
val xorResult  = a xor b
val rightShift = a shr 2
val leftShift  = a shl 2
```

---

> Java

```java
if (object instanceof Car) {
}
Car car = (Car) object;
```

> Kotlin

```kotlin
if (object is Car) {
}
var car = object as Car

// if object is null
var car = object as? Car // var car = object as Car?
```

---

> Java

```java
if (object instanceof Car) {
   Car car = (Car) object;
}
```

> Kotlin

```kotlin
if (object is Car) {
   var car = object // smart casting
}

// if object is null
if (object is Car?) {
   var car = object // smart casting, car will be null
}
```

---

> Java

```java
if (score >= 0 && score <= 300) { }
```

> Kotlin

```kotlin
if (score in 0..300) { }
```

---

> Java

```java
int score = // some score;
String grade;
switch (score) {
	case 10:
	case 9:
		grade = "Excellent";
		break;
	case 8:
	case 7:
	case 6:
		grade = "Good";
		break;
	case 5:
	case 4:
		grade = "OK";
		break;
	case 3:
	case 2:
	case 1:
		grade = "Fail";
		break;
	default:
	    grade = "Fail";				
}
```

> Kotlin

```kotlin
var score = // some score
var grade = when (score) {
	9, 10 -> "Excellent"
	in 6..8 -> "Good"
	4, 5 -> "OK"
	in 1..3 -> "Fail"
	else -> "Fail"
}
```

---

> Java

```java
for (int i = 1; i <= 10 ; i++) { }

for (int i = 1; i < 10 ; i++) { }

for (int i = 10; i >= 0 ; i--) { }

for (int i = 1; i <= 10 ; i+=2) { }

for (int i = 10; i >= 0 ; i-=2) { }

for (String item : collection) { }

for (Map.Entry<String, String> entry: map.entrySet()) { }
```

> Kotlin

```kotlin
for (i in 1..10) { }

for (i in 1 until 10) { }

for (i in 10 downTo 0) { }

for (i in 1..10 step 2) { }

for (i in 10 downTo 1 step 2) { }

for (item in collection) { }

for ((key, value) in map) { }
```

---

> Java

```java
final List<Integer> listOfNumber = Arrays.asList(1, 2, 3, 4);

final Map<Integer, String> keyValue = new HashMap<Integer, String>();
map.put(1, "Amit");
map.put(2, "Ali");
map.put(3, "Mindorks");

// Java 9
final List<Integer> listOfNumber = List.of(1, 2, 3, 4);

final Map<Integer, String> keyValue = Map.of(1, "Amit",
                                             2, "Ali",
                                             3, "Mindorks");
```

> Kotlin

```kotlin
val listOfNumber = listOf(1, 2, 3, 4)
val keyValue = mapOf(1 to "Amit",
                     2 to "Ali",
                     3 to "Mindorks")
```

---

> Java

```java
// Java 7 and below
for (Car car : cars) {
  System.out.println(car.speed);
}

// Java 8+
cars.forEach(car -> System.out.println(car.speed));

// Java 7 and below
for (Car car : cars) {
  if (car.speed > 100) {
    System.out.println(car.speed);
  }
}

// Java 8+
cars.stream().filter(car -> car.speed > 100).forEach(car -> System.out.println(car.speed));
```

> Kotlin

```kotlin
cars.forEach {
    println(it.speed)
}

cars.filter { it.speed > 100 }
      .forEach { println(it.speed)}

// kotlin 1.1+
cars.stream().filter { it.speed > 100 }.forEach { println(it.speed)}
cars.parallelStream().filter { it.speed > 100 }.forEach { println(it.speed)}
```

---

> java

```java
String[] splits = "param=car".split("=");
String param = splits[0];
String value = splits[1];
```


> kotlin

```kotlin
val (param, value) = "param=car".split("=")
```

---

> Java

```java
void doSomething() {
   // logic here
}
```

> Kotlin

```kotlin
fun doSomething() {
   // logic here
}
```

---

> Java

```java
void doSomething(int... numbers) {
   // logic here
}
```

> Kotlin

```kotlin
fun doSomething(vararg numbers: Int) {
   // logic here
}
```

---

> Java

```java
int getScore() {
   // logic here
   return score;
}
```

> Kotlin

```kotlin
fun getScore(): Int {
   // logic here
   return score
}

// as a single-expression function

fun getScore(): Int = score

// even simpler (type will be determined automatically)

fun getScore() = score // return-type is Int
```

---

> Java

```java
int getScore(int value) {
    // logic here
    return 2 * value;
}
```

> Kotlin

```kotlin
fun getScore(value: Int): Int {
   // logic here
   return 2 * value
}

// as a single-expression function
fun getScore(value: Int): Int = 2 * value

// even simpler (type will be determined automatically)

fun getScore(value: Int) = 2 * value // return-type is int
```

---

> Java

```java
public class Utils {

    private Utils() {
      // This utility class is not publicly instantiable
    }

    public static int getScore(int value) {
        return 2 * value;
    }

}
```

> Kotlin

```kotlin
class Utils private constructor() {

    companion object {

        fun getScore(value: Int): Int {
            return 2 * value
        }

    }
}

// another way

object Utils {

    fun getScore(value: Int): Int {
        return 2 * value
    }

}
```

---

> Java

```java
public class Developer {

    private String name;
    private int age;

    public Developer(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;

        Developer developer = (Developer) o;

        if (age != developer.age) return false;
        return name != null ? name.equals(developer.name) : developer.name == null;

    }

    @Override
    public int hashCode() {
        int result = name != null ? name.hashCode() : 0;
        result = 31 * result + age;
        return result;
    }

    @Override
    public String toString() {
        return "Developer{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
```

> Kotlin

```kotlin
data class Developer(var name: String, var age: Int)

```

---

> Java

```java
public class Developer implements Cloneable {

    private String name;
    private int age;

    public Developer(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    protected Object clone() throws CloneNotSupportedException {
        return (Developer)super.clone();
    }
}

// cloning or copying
Developer dev = new Developer("Mindorks", 30);
try {
    Developer dev2 = (Developer) dev.clone();
} catch (CloneNotSupportedException e) {
    // handle exception
}

```

> Kotlin

```kotlin
data class Developer(var name: String, var age: Int)

// cloning or copying
val dev = Developer("Mindorks", 30)
val dev2 = dev.copy()
// in case you only want to copy selected properties
val dev2 = dev.copy(age = 25)

```

---

> Java

```java
public class Utils {

    private Utils() {
      // This utility class is not publicly instantiable
    }

    public static int triple(int value) {
        return 3 * value;
    }

}

int result = Utils.triple(3);

```

> Kotlin

```kotlin
fun Int.triple(): Int {
  return this * 3
}

var result = 3.triple()
```

---

> Java

```java
Person person;
```

> Kotlin

```kotlin
internal lateinit var person: Person
```


---

### Important things to know in Kotlin
* [Learn Kotlin - lateinit vs lazy](https://mindorks.com/blog/learn-kotlin-lateinit-vs-lazy)
* [Learn Kotlin - apply vs with](https://mindorks.com/blog/learn-kotlin-apply-vs-with)
* [Learn Kotlin - Data Class](https://mindorks.com/blog/learn-kotlin-data-class)
* [Learn Kotlin - Destructuring Declarations](https://mindorks.com/blog/learn-kotlin-destructuring-declarations)
* [Learn Kotlin - Extension Functions](https://mindorks.com/blog/learn-kotlin-extension-functions)
* [Learn Kotlin - Sealed Classes](https://mindorks.com/blog/learn-kotlin-sealed-classes)

### Found this project useful :heart:
* Support by clicking the :star: button on the upper right of this page. :v:

[Check out Mindorks awesome open source projects here](https://mindorks.com/open-source-projects)


### License
```
   Copyright (C) 2017 MINDORKS NEXTGEN PRIVATE LIMITED

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
```

### Contributing to From Java To Kotlin
Just make a pull request. You are in!
