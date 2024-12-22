### What is SOLID ?
## The SOLID principles are a set of guidelines for writing high-quality, maintainable, and scalable software
## SOLID নীতিগুলো প্রোগ্রামিংয়ের এমন কিছু গাইডলাইন, যেগুলো কোডকে সহজ, মেইনটেইনেবল, এবং স্কেলেবল করে। এগুলোকে মনে রাখা সহজ এবং এগুলো ফলো করলে কোড ভালো ডিজাইন করা যায়।
## SOLID Stands For
  1. Single Responsibility Principle (SRP)
  2. Open-Closed Principle (OCP)
  3. Liskov Substitution Principle (LSP)
  4. Interface Segregation Principle (ISP)
  5. Dependency Inversion Principle (DIP)
     
### Single Responsibility Principle (SRP)
  1. The Single Responsibility Principle (SRP) states that a class should have only one reason to change, or in other words, it should have only one responsibility. This means that a class should have only one job to do, and it should do it well.
  2. If a class has too many responsibilities, it can become hard to understand, maintain, and modify.
### Single Responsibility Principle (SRP)
  1. একটা ক্লাসের একটাই কাজ থাকবে।
  2. একটা ক্লাস অনেক কাজ করলে সেটা মেইনটেইন করা কঠিন হয়।
  3. উদাহরণ: যদি User ক্লাস থাকে, তাহলে সেটা শুধু ইউজারের তথ্য ম্যানেজ করবে। ইমেইল সেন্ড বা ডাটাবেসের কাজের জন্য আলাদা ক্লাস বানানো উচিত, যেমন EmailService বা UserRepository।

### Open-Closed Principle (OCP)
  1. The Open-Closed Principle (OCP) states that software entities (classes, modules, functions, and so on) should be open for extension but closed for modification. This means that the behavior of a software entity can be extended without modifying its source code.
  2. The OCP is essential because it promotes software extensibility and maintainability. By allowing software entities to be extended without modification, developers can add new functionality without the risk of breaking existing code. This results in code that is easier to maintain, extend, and reuse.
### Open-Closed Principle (OCP)
  1. কোড পরিবর্তন না করে নতুন ফিচার যোগ করা যাবে।
  2. কোড এমনভাবে লিখতে হবে যাতে নতুন কিছু যোগ করতে হলে পুরোনো কোড এডিট না করতে হয়।
  3. উদাহরণ: যদি Shape নামে একটা ক্লাস থাকে, তাহলে নতুন শেপ (যেমন Circle, Square) যোগ করতে চাইলে Shape ক্লাসে পরিবর্তন করার দরকার হবে না।

### Liskov Substitution Principle (LSP)
  1. The Liskov Substitution Principle states that objects of a superclass should be replaceable with objects of its subclasses without affecting the correctness of the program.
  2. In more simple terms, if class A is a subtype of class B, you should be able to replace B with A without breaking the behavior of your program.
  3. সাবক্লাসের অবজেক্ট সুপারক্লাসের মতো কাজ করবে।
  4. বেস ক্লাস ঠিকমতো কাজ করবে না এমন সাবক্লাস বানানো যাবে না।
  5. উদাহরণ: যদি Bird ক্লাসে fly() ফাংশন থাকে, তাহলে Penguin ক্লাস (যা উড়তে পারে না) Bird ক্লাস থেকে ইনহেরিট করা উচিত নয়।

### Interface Segregation Principle (ISP)
  1. The Interface Segregation Principle (ISP) focuses on designing interfaces that are specific to their client's needs. It states that no client should be forced to depend on methods it does not use.
  2. The principle suggests that instead of creating a large interface that covers all the possible methods, it's better to create smaller, more focused interfaces for specific use cases.
  3. যা দরকার নেই, এমন বড় ইন্টারফেস ব্যবহার করা যাবে না।
  4. ইন্টারফেস ছোট এবং নির্দিষ্ট হওয়া উচিত।
  5. উদাহরণ: যদি Animal ইন্টারফেসে fly(), swim(), এবং run() থাকে, তাহলে যেসব প্রাণী উড়তে বা সাঁতরাতে পারে না, তাদের জন্য এটা ঠিক হবে না। বরং Flyable, Swimmable আলাদা ইন্টারফেস বানাতে হবে।

### Dependency Inversion Principle (DIP)
  `1. The Dependency Inversion Principle (DIP) states that high-level modules should not depend on low-level modules, but both should depend on abstractions. Abstractions should not depend on details – details should depend on abstractions.
   2. This principle aims to reduce coupling between modules, increase modularity, and make the code easier to maintain, test, and extend.
   3. কোড কনক্রিটের উপর না, অ্যাবস্ট্রাকশনের উপর নির্ভর করবে।
   4. বড় ক্লাস বা নির্দিষ্ট কিছু ডিপেন্ডেন্সি না করে, অ্যাবস্ট্রাকশন (ইন্টারফেস) ব্যবহার করা ভালো।
   5. উদাহরণ: PaymentProcessor যদি সরাসরি PayPalService ব্যবহার করে, তাহলে পরিবর্তন কঠিন হবে। এর বদলে PaymentService নামে একটা ইন্টারফেস ব্যবহার করলে সেটার উপর নির্ভরশীল থাকা ভালো।







