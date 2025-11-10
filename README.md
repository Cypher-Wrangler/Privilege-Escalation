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

- When attackers compromise accounts and sign in, the login events tend to generate either a logon type  3 - network logon or logon type 10 - remote desktop. Type 10 is the most common way to gain access into an environment due to a lot of org having RDP exposed to public
- Logon type 3
   <img width="1299" height="506" alt="image" src="https://github.com/user-attachments/assets/9d6331a7-efc9-4070-a863-2c2e39578836" />
- Logon type 10 - generates workable events
   <img width="1376" height="403" alt="Screenshot 2025-11-10 132715" src="https://github.com/user-attachments/assets/e54bc0d7-c155-4d89-8e66-5c4195b7fb3f" />
- Lookin at the earliest event:
   On 1/26/24 2:17:22.000 PM there was successfully RDP log in on ComputerName=DESKTOP-J78SBRN.MyDFIR.local using the account Administrator
  <img width="1078" height="1241" alt="image" src="https://github.com/user-attachments/assets/301d76f1-b204-4a96-966c-8fe2a901c402" />
- This activity was from an IP address 192.168.100.181 which was discovered during 
   

















