### What is a signal in Django?
1. Django-তে signal হলো একটি পদ্ধতি যার মাধ্যমে কোনো ইভেন্ট ঘটলে সেই ইভেন্ট সম্পর্কে অন্য অংশকে জানানো হয়। এটি আপনার অ্যাপ্লিকেশনের এক অংশকে অন্য অংশ থেকে স্বাধীনভাবে কাজ করতে দেয়। সিগন্যাল ব্যবহারের মাধ্যমে আপনি কোনো মডেল সেভ করার আগে বা পরে কিছু অ্যাকশন সম্পাদন করতে পারেন।
2. Django-তে সিগন্যাল এমন একটি সিস্টেম যা অ্যাপ্লিকেশনটির এক অংশে কোনো ইভেন্ট ঘটলে অন্য অংশকে তা জানানোর কাজ করে। এটি একটি "বার্তাবাহক" হিসেবে কাজ করে যা বিভিন্ন অংশের মধ্যে কোড সংযোগ ছাড়াই ইভেন্টের খবর দেয়।
3. In Django, signals are a way to allow decoupled applications to get notified when certain actions occur elsewhere in the application. They work like "messengers" that inform specific parts of your application about events without tightly coupling the logic.


### Signal ব্যবহার কখন প্রয়োজন?
  1. মডেল সেভ করার আগে বা পরে কোনো কাজ করতে, যেমন ইমেইল পাঠানো বা লগ করা।
  2. অ্যাপ্লিকেশনটির বিভিন্ন অংশের মধ্যে কম্পোনেন্টাল যোগাযোগ বজায় রাখতে।
  3. যখন কোনো ইভেন্টের পরে স্বয়ংক্রিয়ভাবে কিছু করতে হয়, যেমন: মডেল সেভ বা ডিলিট করার পরে।
  4. অ্যাপ্লিকেশনের লজিক পরিষ্কার এবং আলাদা রাখতে চাইলে।


### Post_save (সেভ করার পরে)
  1. যখন কোনো মডেল সেভ করা হয়, তার পরবর্তী সময়ে আপনি কিছু করতে চাইলে post_save সিগন্যাল ব্যবহার করা হয়। যেমন, কোনো মেসেজ বা ইমেইল পাঠানো।
     ```
     from django.db.models.signals import post_save
      from django.dispatch import receiver
      from django.contrib.auth.models import User
      from django.core.mail import send_mail
      
      # Post-save signal: সেভ করার পরে মেসেজ পাঠানো
      @receiver(post_save, sender=User)
      def send_welcome_email(sender, instance, created, **kwargs):
          if created:  # শুধুমাত্র নতুন ইউজার তৈরি হলে
              send_mail(
                  'Welcome to our site!',
                  f'Hello {instance.username}, welcome to our platform!',
                  'from@example.com',
                  [instance.email],
                  fail_silently=False,
              )

     ```
 2. এখানে post_save সিগন্যাল ব্যবহার করা হয়েছে যখন User মডেলটি সেভ হয়।
 3. যখন নতুন ইউজার তৈরি হয়, তখন তাকে একটি স্বাগতম ইমেইল পাঠানো হবে।
### Pre_save (সেভ করার আগে)
  1. যখন আপনি চান যে, কোনো মডেল সেভ করার আগে কিছু চেক বা পরিবর্তন করা হোক, তখন pre_save সিগন্যাল ব্যবহার করা হয়।
     ```
       from django.db.models.signals import pre_save
       from django.db.models.signals import pre_save
      from django.dispatch import receiver
      from django.contrib.auth.models import User
      
      # Pre-save signal: সেভ করার আগে মেসেজ চেক করা
      @receiver(pre_save, sender=User)
      def check_username(sender, instance, **kwargs):
          if 'admin' in instance.username:
              print("Warning: Username contains 'admin', consider changing it!")

     ```
  3. এখানে pre_save সিগন্যাল ব্যবহার করা হয়েছে User মডেলটি সেভ হওয়ার আগে।
  4. যদি ইউজারের নামের মধ্যে "admin" শব্দটি থাকে, তাহলে একটি সতর্কবার্তা প্রিন্ট হবে।



