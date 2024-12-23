### ACID Properties in DBMS
## ACID properties ensure data consistency, integrity, and reliability in a database while performing transactions.
## ACID প্রোপার্টিগুলো ডাটাবেজে ট্রানজ্যাকশন পরিচালনার সময় ডাটার ধারাবাহিকতা (Consistency), অখণ্ডতা (Integrity), এবং নির্ভরযোগ্যতা (Reliability) নিশ্চিত করে।
## Atomicity
  1. A transaction is all or nothing. If any part of the transaction fails, the entire transaction is rolled back, ensuring no partial changes.
  2. একটি ট্রানজ্যাকশন পুরোপুরি হবে বা একেবারে হবে না। যদি কোনো অংশ ব্যর্থ হয়, তাহলে পুরো ট্রানজ্যাকশন বাতিল হয়ে যাবে।
  3. (উদাহরণ): যদি একটি অ্যাকাউন্ট থেকে টাকা কেটে আরেকটিতে জমা দেওয়ার সময় সমস্যা হয়, তবে পুরো লেনদেন বাতিল হবে।
## Consistency
  1. A transaction must maintain database rules, ensuring the database remains in a valid state before and after the transaction.
  2. একটি ট্রানজ্যাকশন ডাটাবেজের নিয়ম মেনে চলে এবং ট্রানজ্যাকশনের আগে এবং পরে ডাটাবেজকে সঠিক অবস্থায় রাখে।
  3. (উদাহরণ): একটি ব্যাংকের মোট টাকা লেনদেনের আগে এবং পরে একই থাকবে।
