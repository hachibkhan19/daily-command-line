#### How to create a branch
```
git branch (branch_name)
```
#### How to delete a branch. Before deleting a branch, make sure you are not on the branch you want to delete. You can switch to a different branch using the git checkout command.
```
git branch -d (branch_name)
```
#### To create a new branch and switch to it
```
git checkout -b new_branch_name
```
### How to clone code from a specific branch from remote repo
 ```
  git clone -b dev git@git.inneedcloud.com.bd:InNeed/Quantlio_Stratus.git
  or
  git clone -b dev https://git.inneedcloud.com.bd/InNeed/Quantlio_Stratus.git

 ```
### git config pull.rebase false
```
  যখন আপনি git config pull.rebase false সেটিং ব্যবহার করেন, তখন git pull করার সময় যদি আপনার লোকাল ব্রাঞ্চে কিছু পরিবর্তন থাকে এবং রিমোট ব্রাঞ্চেও কিছু পরিবর্তন থাকে, তাহলে Git আপনার লোকাল ব্রাঞ্চে রিমোট ব্রাঞ্চের পরিবর্তনগুলোর    সঙ্গে মার্জ (merge) করবে।
```
1. এটি এমন একটি প্রক্রিয়া, যেখানে:
   * আপনার লোকাল ব্রাঞ্চে যেসব কমিট করা হয়েছে তা রিমোট ব্রাঞ্চের পরিবর্তনের সাথে একত্রিত হয়।
   * যদি দুটি ব্রাঞ্চের মধ্যে কোনো কনফ্লিক্ট না থাকে, তবে Git সাধারণত মার্জ কমিট তৈরি করে, যা দুইটি ব্রাঞ্চের ইতিহাস একত্রিত করে।
   * যদি কোনো কনফ্লিক্ট থাকে, তাহলে আপনাকে ম্যানুয়ালি কনফ্লিক্ট সলভ করতে হবে এবং তারপর মার্জ কমিট করতে হবে।

এই ধরনের মার্জ পদ্ধতিতে, আপনার ব্রাঞ্চের ইতিহাসে মার্জ কমিট দেখা যাবে, যা দেখায় কখন এবং কোথায় আপনার লোকাল পরিবর্তন এবং রিমোট পরিবর্তন একত্রিত হয়েছে।
## উদাহরণ:
```
  ধরা যাক, আপনি একটি ফিচার ব্রাঞ্চে কাজ করছেন এবং আপনার কমিট আছে। একই সময়, রিমোট ব্রাঞ্চে অন্য কেউ পরিবর্তন করেছে। আপনি যখন git pull করবেন (যেখানে pull.rebase false কনফিগার করা আছে), তখন Git এই দুটি ব্রাঞ্চকে মার্জ   
  করবে, এবং মার্জ কমিট তৈরি হবে, যা ইতিহাসে দেখাবে যে আপনার কাজ এবং অন্যের কাজ একত্রিত হয়েছে।
```
