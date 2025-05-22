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

ansible-whatsapp-reminder-bot/
├── data/             # Reminders and messages
├── inventory/        # Ansible inventory
├── roles/
│   └── notifier/
│       ├── tasks/
│       └── templates/
├── vars/             # Twilio credentials (excluded via .gitignore)
├── playbook.yml      # Main Ansible playbook
└── README.md


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

5. 🔁 Schedule with Cron
  TZ=America/Chicago
0 17 * * 1 [ $(expr $(date +\%s) / 604800 \% 2) -eq 0 ] && cd ~/ansible-daily-notifier && /usr/bin/ansible-playbook -i inventory/localhost.ini playbook.yml

📸 Demo Screenshot
![IMG_8540](https://github.com/user-attachments/assets/91d1e3b3-c37c-44cb-86d8-bef394eb350e)

👨‍💻 Author

Sainath Reddy
[GitHub](https://github.com/sainathp8930)| [LinkedIn](https://www.linkedin.com/in/sainath-reddy-5947ba125/)

📄 License

MIT License (recommended)
