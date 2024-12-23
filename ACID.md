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
## Isolation
  1. Multiple transactions happening at the same time should not interfere with each other. They must act as if executed one after the other.
  2. একই সময়ে একাধিক ট্রানজ্যাকশন হলে, সেগুলো একে অপরকে প্রভাবিত করবে না। মনে হবে যে, ট্রানজ্যাকশনগুলো আলাদাভাবে একের পর এক হচ্ছে।
  3. (উদাহরণ): যদি দুইজন ইউজার একসঙ্গে শেষ একটি টিকিট কিনতে চায়, তবে একজনই সফল হবে।

## Durability
  1. Once a transaction is committed, its changes are permanent, even in case of a system crash.
  2. একটি ট্রানজ্যাকশন সম্পন্ন হলে, তার পরিবর্তন স্থায়ী হয়ে যায়, এমনকি সিস্টেম ক্র্যাশ হলেও।
  3. (উদাহরণ): ইউজার যদি একটি প্রোফাইল আপডেট করে এবং সেটি সেভ হয়, তবে সিস্টেম রিস্টার্ট হলেও সেই পরিবর্তন থাকবে।
