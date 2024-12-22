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
