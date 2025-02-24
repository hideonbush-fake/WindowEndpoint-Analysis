# Window Endpoint-Analysis

## Objective
As part of the challenge provided by TCM, I will execute a malicious executable on my Windows VM and analyze its behavior. Using only my infected endpoint, I will gather critical Indicators of Compromise (IOCs) to understand its impact and potential threats.

### Skills Learned

- Acquired hands-on experience in system analysis, extracting key security insights and detecting anomalies through forensic investigation of Window system.
- Developed a deeper understanding of Window Operating System

### Tools Used

- CMD.exe
- Window Event Viewer

## Investigate the Malicious Executable
![Screenshot 2025-02-24 142709](https://github.com/user-attachments/assets/25eb8ba2-1bbd-44c8-9954-43db3a8be159)
![Screenshot 2025-02-24 142808 (1)](https://github.com/user-attachments/assets/ca9607c9-55be-4df9-b907-0dbe5c287ac1)
- Malware is listening on port 50050
- Process ID of 7140

List out all the DLL modules loaded for this executable
![Screenshot 2025-02-24 143000](https://github.com/user-attachments/assets/675e9ad9-6450-472b-96bb-3945e52550e9)

Get Command Line

![Screenshot 2025-02-24 143640](https://github.com/user-attachments/assets/e78fce76-9097-402d-9add-77adcb3b7764)
- Adversary opened up a terminal and executed the executable

Find the Parent Process

![Screenshot 2025-02-24 143628 (1)](https://github.com/user-attachments/assets/72995d91-4540-4afc-b71a-5bd3dca6be49)
- Executed from CMD.exe

Are there any shared resources the Adversary created to exfil data or gather information about other compromising system
![Screenshot 2025-02-24 144837 (2)](https://github.com/user-attachments/assets/da0c6401-e1f7-4541-b605-fe55806313e7)
- The adversary has created a share file named "xkalibur" under the Temp Folder

Check for RUN entries on Window Registry to check if the adversary created a persistence on the system.

![Screenshot 2025-02-24 143838](https://github.com/user-attachments/assets/15b8777f-a437-4dfd-aa0c-9e827aa54ae6)
- The malicious entry the adversary created is "CleanUpController"
- ImagePath: C:\Users\tcm\Downloads\wininit.exe

  















