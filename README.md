![GitHub last commit](https://img.shields.io/github/last-commit/sainathp8930/ansible-whatsapp-reminder-bot)
![GitHub repo size](https://img.shields.io/github/repo-size/sainathp8930/ansible-whatsapp-reminder-bot)
![GitHub license](https://img.shields.io/github/license/sainathp8930/ansible-whatsapp-reminder-bot?style=flat)

This project automates WhatsApp reminders using **Ansible**, **Twilio**, and a **cron job**.  
It’s designed to help you and your roommates stay on top of groceries, chores, and household tasks — all via WhatsApp 📲

---

## 🚀 Features

- 🧾 Sends WhatsApp reminders using Twilio API
- 👨‍👨‍👦 Supports multiple recipients
- 🗂 YAML-based task structure (editable by non-tech users)
- 🛠 Built with Ansible roles, templates, and variables
- ⏰ Cron-based scheduler (bi-weekly, 5 PM CST)
- 💬 Local message preview

---

## 📂 Folder Structure

![image](https://github.com/user-attachments/assets/c8c050fd-7ed3-46c8-be6c-b1a3c139624e)



---

## 🛠 Requirements

- Ansible (2.10+)
- Twilio Account (Sandbox for WhatsApp)
- AWS EC2 (or any Linux host)
- Git + Cron

---

## ⚙️ Setup Instructions

1. Clone this repo:
   ```bash
   git clone git@github.com:sainathp8930/ansible-whatsapp-reminder-bot.git
   cd ansible-whatsapp-reminder-bot

2.	Add your Twilio credentials to vars/main.yml:
   twilio_sid: "ACxxxxxxxxxxxx"
   twilio_token: "your_twilio_token"
   twilio_from: "whatsapp:+123456789"
3.	Edit your task content in:
     data/daily_reminders.yml

4. Run it:
   ansible-playbook -i inventory/localhost.ini playbook.yml

![Screenshot 2025-05-22 at 4 51 11 PM](https://github.com/user-attachments/assets/986fc87e-df0c-48b1-9e03-61ae239e553c)




5. 🔁 Schedule with Cron
  TZ=America/Chicago
0 17 * * 1 [ $(expr $(date +\%s) / 604800 \% 2) -eq 0 ] && cd ~/ansible-daily-notifier && /usr/bin/ansible-playbook -i inventory/localhost.ini playbook.yml

📸 Demo Screenshot
![image](https://github.com/user-attachments/assets/136d175b-ccca-44c7-9af6-267ff89744be)


👨‍💻 Author

Sainath Reddy Pentala
[GitHub](https://github.com/sainathp8930)| [LinkedIn](https://www.linkedin.com/in/sainath-reddy-5947ba125/)

📄 License

MIT License (recommended)
