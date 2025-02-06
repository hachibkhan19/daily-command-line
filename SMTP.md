### How to Send Email with Django
### Django to send emails with SMTP
    Step1: First Need to Configuration For SMTP and In your settings.py file, add the following code:
    Step2: Sign in to your google account and click on Manage account.
    
![Screenshot](https://github.com/user-attachments/assets/fe49d835-6e07-4134-a522-272f2598041d)

![Screenshot from 2025-02-06 10-48-40](https://github.com/user-attachments/assets/9bbaed2f-8606-49f4-9438-4dc66b02124d)


Step 3: Enable two factor authentication by typing “2 step verification” on the search bar.

![Screenshot from 2025-02-06 10-49-45](https://github.com/user-attachments/assets/d94030e4-0c08-4680-bab8-8a16a2e5af24)

    
Step 4: After enabling 2FA, type “App passwords” on the search bar.

![Screenshot from 2025-02-06 10-50-29](https://github.com/user-attachments/assets/9864db6a-b733-4c59-a9c6-3a0e673d3515)


Step 5: 
    Enter a project name and your unique password will be provided to use it in your project. Note that the password is only shown once, and it is valid until it is manually removed from the app passwords tab. Hence copy the password when it is shown and use it as EMAIL_HOST_PASSWORD in the Django settings.py file.
    
  ![Screenshot from 2025-02-06 10-54-59](https://github.com/user-attachments/assets/dddbba16-a6da-4d0e-8a34-ed46807e3d95)

    Step 6: Generate App Password
![Screenshot from 2025-02-06 10-55-53](https://github.com/user-attachments/assets/0d3a611f-5f80-4ee1-b151-638817bab9cc)

  Step 7: 
    ```
    # Email settings for sending email using Gmail SMTP
    EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
    EMAIL_HOST = 'smtp.gmail.com'
    EMAIL_PORT = 587
    EMAIL_USE_TLS = True
    EMAIL_HOST_USER = 'hachibkhancse12@gmail.com'  # Replace with your Gmail address
    EMAIL_HOST_PASSWORD = 'ybxn rqzg jajh ehmr'  # Use your app password, not Gmail password
    DEFAULT_FROM_EMAIL = EMAIL_HOST_USER
    ```
