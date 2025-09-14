# Major Features introduced in Various Java versions

Here is a detailed list of major features introduced in each Java version from Java 5 to the latest (Java 20), including evolution of some features like the switch statement. The list includes feature explanations and code examples where applicable.

| Java Version | Features & Explanation | Code Example / Notes |
|--------------|------------------------|---------------------|
| **Java 5 (2004)** | 1. **Generics**: Compile-time type safety for collections, reducing casts.<br>2. **Enhanced for-each loop**: Simplified iteration over arrays/collections.<br>3. **Autoboxing/Unboxing**: Automatic conversion between primitives and wrapper classes.<br>4. **Annotations**: Metadata added to classes/methods for tools/frameworks.<br>5. **Enumerations (enum)**: Type-safe constant sets.<br>6. **Varargs**: Methods accepting variable number of arguments.<br>7. **Static import**: Import static members for cleaner code. | ```java\n// Generics\nList<String> list = new ArrayList<>();\nlist.add(\"Hello\");\nString s = list.get(0);\n\n// foreach\nint[] nums = {1,2,3};\nfor (int n : nums) System.out.println(n);\n\n// Autoboxing\nInteger i = 10; int j = i; // automatic conversion\n\n// Enum\nenum Day {MON, TUE, WED}\nDay today = Day.MON;\n\n// Varargs\nvoid print(String... args) { for (String s : args) System.out.println(s); }\n\n// Static import\nimport static java.lang.Math.PI;\nSystem.out.println(PI);\n```
| **Java 6 (2006)** | 1. **Scripting API**: Integration with scripting languages via javax.script.<br>2. **Pluggable Annotation Processing**<br>3. **Web Services APIs** (JAXB, JAX-WS, StAX)<br>4. **Improved Swing and Desktop integration**<br>5. **Console class**: Console input/output support | Java 6 focused more on APIs and tooling improvements than language changes. |
| **Java 7 (2011)** | 1. **Strings in switch**: switch statement supports String.<br>2. **Try-with-resources**: Automatic resource management.<br>3. **Diamond operator (`<>`)**: Type inference in generics.<br>4. **Multi-catch exceptions**: Catch multiple exceptions in one block.<br>5. **Binary literals and underscores in numbers**<br>6. **Fork/Join framework**<br>7. **NIO.2 File API** enhancements | ```java\n// String in switch\nString fruit = \"apple\";\nswitch(fruit) {\n  case \"apple\": System.out.println(\"Apple\"); break;\n}\n\n// Try-with-resources\ntry (BufferedReader br = new BufferedReader(new FileReader(\"file.txt\"))) {\n  System.out.println(br.readLine());\n}\n```
| **Java 8 (2014)** | 1. **Lambda expressions**: Functional programming support.<br>2. **Functional interfaces**<br>3. **Streams API**: Sequence of elements with aggregate operations.<br>4. **Default methods in interfaces**<br>5. **Method references**<br>6. **New Date/Time API (java.time)**<br>7. **Optional class** for null safety<br>8. **`forEach()` method in Iterable** | ```java\n// Lambda\nList<String> list = Arrays.asList(\"a\", \"b\");\nlist.forEach(s -> System.out.println(s));\n\n// Stream\nlist.stream()\n    .filter(s -> s.startsWith(\"a\"))\n    .forEach(System.out::println);\n\n// Default methods\ninterface MyInterface {\n  default void defaultMethod() { System.out.println(\"default\"); }\n}\n```
| **Java 9 (2017)** | 1. **Module System (JPMS)**: Modularize applications.<br>2. **JShell**: Interactive REPL for Java.<br>3. **Private methods in interfaces**<br>4. **Factory methods for immutable collections**<br>5. **Improvements in Stream API**<br>6. **HTTP/2 Client API (incubator)** | ```java\n// Factory methods\nList<String> list = List.of(\"a\", \"b\");\n\n// Private method in interface\ninterface I {\n  private void helper() {}\n  default void m() { helper(); }\n}\n```
| **Java 10 (2018)** | 1. **Local variable type inference (`var`)**<br>2. **Additional unmodifiable collection APIs in Collectors**<br>3. Other minor JVM improvements | ```java\nvar list = new ArrayList<String>();\nlist.add(\"a\");\n```
| **Java 11 (2018)** | 1. **New String methods:** `isBlank()`, `lines()`, `strip()`, `repeat()`<br>2. **Local-variable syntax for lambda parameters** (using `var`)<br>3. Other API improvements and deprecated features removal | ```java\nString s = \" \";\nSystem.out.println(s.isBlank()); // true\n\n\"a\\nb\".lines().forEach(System.out::println);\n\nString repeated = \"Hi\".repeat(3); // \"HiHiHi\"\n\n// Lambda with var\nlist.forEach((var item) -> System.out.println(item));\n```
| **Java 12 (2019)** | 1. **Switch expressions preview**: switch can be used as expression with `->` and yield.<br>2. JVM constants API<br>3. Microbenchmark suite and other JVM improvements | ```java\nint day = 3;\nString result = switch(day) {\n  case 1 -> \"Mon\";\n  case 2 -> \"Tue\";\n  default -> \"Other\";\n};\n```
| **Java 13 (2019)** | 1. **Text blocks (preview)**: Multiline string literals | ```java\nString textBlock = \"\"\"\nHello\nWorld\n\"\"\";\n```
| **Java 14 (2020)** | 1. **Records (preview)**: Compact syntax for data classes<br>2. **Switch expressions (standardized)**<br>3. Helpful NullPointerExceptions | ```java\nrecord Point(int x, int y) {}\nPoint p = new Point(1, 2);\n```
| **Java 15 (2020)** | 1. **Sealed classes (preview)**: Controlled inheritance<br>2. Text blocks standardized | |
| **Java 16 (2021)** | 1. Records and pattern matching for instanceof finalized<br>2. Vector API (incubator) | |
| **Java 17 (2021, LTS)** | 1. Sealed classes finalized<br>2. Strong encapsulation of JDK internals<br>3. Pattern matching for switch (preview) | |
| **Java 18 to 20 (2023-2024)** | Latest versions with features like: scoped values, structured concurrency, new UTF-8 charset, unnamed classes, key encapsulation, and incremental JVM improvements | |

### Evolution of switch statement:
- Introduced in early versions as a statement for primitives and enums.
- Java 7 added support for Strings.
- Java 12 introduced switch expressions (preview) with `->` syntax, enabling switch to return values and eliminate fall-through by default. The `yield` keyword was added for multi-statement cases.
- Java 14 standardized switch expressions and enhanced pattern matching.
- Java 17 continued to preview pattern matching for switch.

This table and explanation provide a comprehensive view of Java feature evolution from Java 5 to the latest, covering language enhancements, APIs, and evolved features like `switch`. Full code examples are given for key features to help illustrate usage.

**Sources**

[1] JDK 5 New Features https://www3.ntu.edu.sg/home/ehchua/programming/java/JDK5_NewFeatures.html

[2] New Features in Java 7 https://www.whizlabs.com/blog/new-features-in-java-7/

[3] Java 8 Features - Complete Tutorial https://www.geeksforgeeks.org/java/java-8-features/

[4] Java 8, 9, 10 to 21 new key features and enhancements https://www.aegissofttech.com/articles/java-8-9-10-11-new-key-features-and-enhancements.html

[5] New Features of Java 12 https://www.geeksforgeeks.org/java/new-features-of-java-12/

[6] Java 9 Features with Examples https://www.geeksforgeeks.org/java/java-9-features-with-examples/

[7] Experiences with the New Java 5 Language Features http://www.oracle.com/technical-resources/articles/java/java-5-features.html

[8] New Features and Enhancements J2SE 5.0 https://docs.oracle.com/javase/1.5.0/docs/relnotes/features.html

[9] Java Features https://www.geeksforgeeks.org/java/java-features/

[10] Java 5 Features https://www.codeproject.com/Articles/27741/Java-5-Features

[11] jdk 1.6 features | Java-Techies Blog - WordPress.com https://harnarayanvishwakarma.wordpress.com/interview-questions/core-java/jdk-1-6-features/

[12] Java 9 Features | ODP https://www.slideshare.net/slideshow/java-9-features-94861306/94861306

[13] Java 11: New Features and Enhancements with Examples https://blog.nashtechglobal.com/java-11-new-features-and-enhancements-with-examples/

[14] Java 5 - javapandit Technologies https://www.javapandit.co.in/java-5.html

[15] Java 6 - javaalmanac.io https://javaalmanac.io/jdk/6/

[16] 55 New Features in Java 7 | PPT https://www.slideshare.net/slideshow/55-things-in-java-7/13310514

[17] Java 8 Features with Examples to Boost Your Code Efficiency https://www.simplilearn.com/java-8-features-article

[18] Java 10 Features and Java 10 tutorial with examples https://javagoal.com/java-10-features/

[19] New Features in Java 11 https://www.baeldung.com/java-11-new-features

[20] Java 12 Features https://www.javaguides.net/2024/08/java-12-features.html
