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
- This activity was from an IP address 192.168.100.181 which was discovered during the EXECUTION PHASE analysis.
- Using EventCode=4672, we can check if the account of interest has administrative privilege: 
   <img width="1088" height="663" alt="image" src="https://github.com/user-attachments/assets/c38287db-1ebe-41a1-ab16-6bc22e47c9fa" />
- Adding source IP to our search Logon_Type has 2 values
   <img width="1045" height="408" alt="image" src="https://github.com/user-attachments/assets/c05b40c7-d73d-4051-b838-9f3392dcf2b2" />
- Then use logon type to see if theres any earliest events: There are 7 events with 2 user accounts( Administrator and sm)
   <img width="1360" height="462" alt="image" src="https://github.com/user-attachments/assets/539bda49-c2dd-4a80-af96-260656d7975f" />
- Looking at the earliest event a successful unauthorised login occurred on 2024-01-26 at 2:13:01:000 UTC
    <img width="1100" height="1148" alt="Screenshot 2025-11-10 141702" src="https://github.com/user-attachments/assets/6463c7ce-827c-4b29-ac66-afaa31e98ccd" />

- We can use login ID to see what other actions were performed during that session 
  <img width="1354" height="874" alt="Screenshot 2025-11-10 142508" src="https://github.com/user-attachments/assets/851d89d4-f1cf-4dfe-8d1c-25d1fbcecf93" />

- Looking at the earliest event We can see special privilege permission were assigned
  <img width="1070" height="1093" alt="Screenshot 2025-11-10 142820" src="https://github.com/user-attachments/assets/5b91be03-c6cf-4fa6-becf-43a5f21977a4" />

# Conclusion
 Using Event ID 4624 under security and filtering specifically for logon types can provide quick results when looking for unauthorized access.















