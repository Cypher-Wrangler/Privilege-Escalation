# Privilege-Escalation
Identifying privilege escalation technique via valid accounts.
A common method for privilege escalation that attackers use to compromise existing accounts via phishing, brute force, credential stuffingetc.
Often this accounts tend to be overly permissive, making it for attackers to perform their actions.

- Look for accounts with successful logins
  <img width="1370" height="1244" alt="image" src="https://github.com/user-attachments/assets/fe4862a5-3746-4c04-b314-a92d05feab5c" />
- As this will includes any computer accounts, system accounts and service accounts, baseline to focus on user accounts.
- Using transforming commands to identify all users
   <img width="1382" height="922" alt="image" src="https://github.com/user-attachments/assets/97a0c3ba-4394-4b91-bf0f-1e4a3132aed2" />
- Theres a few system and service accounts to filter out. Keeping in mind SYSTEM is often targeted and attackers can originate from this account as well.
   <img width="1351" height="550" alt="image" src="https://github.com/user-attachments/assets/555e87de-9b01-49e1-8727-37c2ad1916cc" />

- When attackers compromise accounts and sign in, the login events

















