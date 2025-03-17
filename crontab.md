### পদ্ধতি ১: ক্রন জব (Linux/macOS) 
1. একটি ব্যাকআপ স্ক্রিপ্ট তৈরি করো:
- তোমার Django প্রোজেক্টের ভেতরে backup_db.sh নামে একটি ফাইল তৈরি করো:
  ```
    #!/bin/bash
  
    BACKUP_DIR="/home/hachib-khan/Documents/mcq-be/db_backups"
    mkdir -p $BACKUP_DIR
    
    DATE=$(date +"%Y-%m-%d_%H-%M-%S")
    BACKUP_FILE="$BACKUP_DIR/db_backup_$DATE.sql"
    
    PGPASSWORD="postgres" pg_dump -U postgres -h localhost stable_mcq_db > $BACKUP_FILE

  ```
2. স্টেপ ৩: স্ক্রিপ্টটি এক্সিকিউটেবল (Executable) করা
- স্ক্রিপ্টটি রান করার আগে এটি এক্সিকিউটেবল করতে হবে:
  ```
  chmod +x backup_db.sh
  ```
3. স্টেপ ৪: স্ক্রিপ্ট রান করা
   ```
     ./backup_db.sh
   ```
4. ক্রনজব সেট করা (Linux/macOS):
   ```
     crontab -e
   ```
5. তারপর নিচের লাইনটা অ্যাড করো:
6. * * * * * /bin/bash /home/hachib-khan/Documents/mcq-be/backup_db.sh (Path Folder)
  - এটি প্রতি 1 মিনিট পর পর backup_db.sh রান করবে।
7. এই ক্রোনজবটি প্রতিদিন রাত ১২:০০ AM এ রান হবে এবং backup_db.sh স্ক্রিপ্ট এক্সিকিউট করবে।
```
  0 0 * * * /bin/bash /home/hachib-khan/Documents/mcq-be/backup_db.sh
```

7. ১. Crontab সার্ভিস চালু আছে কিনা চেক করো
```
  sudo systemctl status cron
```
8. 👉 যদি inactive (dead) দেখায়, তাহলে এটি চালু করো:
```
sudo systemctl enable cron

```
## Crontab ইনস্টল ও চালু করার প্রক্রিয়া (Linux Server)
1. Cron ইন্সটল আছে কিনা চেক করো:
   ```
     crontab -l
   ```
2. Cron ইন্সটল করার কমান্ড (Ubuntu/Debian/Linux
   ```
     sudo apt update && sudo apt install cron -y
   ```
3. Cron সার্ভিস চালু করো:
   ```
   sudo systemctl enable cron
   sudo systemctl start cron
   ```
4. সার্ভার রিস্টার্টের পরেও যাতে ক্রন সার্ভিস চালু থাকে:
   ```
     sudo systemctl restart cron
   ```
