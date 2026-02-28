# Digital Forensics Notes & Investigation Handbook

Author: Dev Kumar Sen  
Domain: Digital Forensics & Incident Response (DFIR)  
Level: Beginner → Advanced  
Purpose: Practical forensic investigation reference with tools, techniques, and workflows.

---

## 📘 MODULE 1 – Basics of Digital / Cyber Forensics

---

## 1. Introduction to Digital / Cyber Forensics

Digital Forensics (also known as Cyber Forensics) is a specialized branch of forensic science that deals with identifying, acquiring, preserving, analyzing, authenticating, and reporting digital evidence in a legally acceptable manner.

Digital evidence can be obtained from:
- Computers and laptops
- Mobile devices
- Networks and servers
- Cloud platforms
- Storage media

---

## 2. Cyber Crime & IT Law (India)

Cyber crimes in India are governed by the Information Technology Act, 2000, amended in 2008 (ITAA 2008).

### Common Cyber Crimes and Legal Sections

- Hacking – Section 66, ITAA 2008
- DoS / DDoS Attacks – Section 66, ITAA 2008
- Spreading Virus or Malware – Section 66 or Section 66F, ITAA 2008
- Website Defacement – Section 66, ITAA 2008
- Cyber Terrorism – Section 66F, ITAA 2008

Forensic investigators must correlate technical findings with appropriate legal sections during reporting.

---

## 3. Social Networks as a Cyber Threat

Social networking platforms are major sources of cyber crime and digital evidence.

### Dark Side of Social Networks
- Identity theft
- Cyber stalking
- Online grooming of minors
- Financial fraud and scams
- Social engineering attacks
- Data leakage due to oversharing

Many children interact with unknown people online, and a significant percentage meet online contacts without verifying real identities.

### Forensic Evidence from Social Media
- Chat conversations
- Images and videos
- Metadata
- Deleted messages
- Location history
- Account activity logs

---

## 4. Types of Web

### Surface Web
- Publicly accessible
- Indexed by search engines
- Example: blogs, news sites, company websites

### Deep Web
- Not indexed by search engines
- Requires authentication
- Example: emails, banking portals, cloud storage

### Dark Web
- Accessible via specialized software
- Provides anonymity
- Often used for illegal activities such as data leaks, drugs, weapons, and cyber crime services

Dark web investigations often involve network forensics and cryptocurrency analysis.

---

## 5. Branches of Digital Forensics

- Computer Forensics
- Malware Forensics
- Network Forensics
- Wireless Forensics
- Database Forensics
- Mobile Device Forensics
- Email Forensics
- Memory (RAM) Forensics

Each branch uses specialized tools and techniques.

---

## 6. Digital Forensic Investigation Lifecycle

Standard forensic investigation workflow:

Identification  
→ Acquisition  
→ Preservation  
→ Authentication  
→ Analysis  
→ Reporting  

### Explanation
- Identification: Locate potential evidence sources
- Acquisition: Collect data without altering original evidence
- Preservation: Maintain integrity using hashes and write blockers
- Authentication: Prove evidence originality
- Analysis: Extract meaningful information
- Reporting: Present findings in technical and legal format

---

## 7. Authentication of Digital Evidence

Three key parameters used to authenticate digital evidence:

1. Digital Signature – Confirms authenticity and source
2. Digital Certificate – Validates identity
3. Hash Algorithms – Ensure data integrity (MD5, SHA-1, SHA-256)

Hash values must match before and after analysis.

---

## 8. Chain of Custody

Chain of Custody is the documentation that records:
- Who collected the evidence
- Date and time of collection
- Storage location
- Access history
- Transfers between individuals

A broken chain of custody can make evidence inadmissible in court.

---

## 9. Forensic Process Models

### Dead Forensic Approach
Deals with non-volatile data from powered-off systems.

Includes:
- Data recovery
- File carving
- Signature-based recovery
- Disk analysis

Used when the system is shut down.

---

### Live Forensic Approach
Deals with volatile data from running systems.

Includes:
- RAM analysis
- Malware analysis
- Network connections
- Running processes

Used when immediate response is required.

---

## 10. Digital Evidence

Digital evidence is any probative information stored, processed, or transmitted in electronic form that can be presented in a court of law.

Examples:
- Emails
- Logs
- Images and videos
- Chat messages
- Memory dumps
- Network traffic captures

---
## 📘 MODULE 2 – Evidence Acquisition Techniques

---

## 1. Hashing Mechanism

Hashing is a fundamental technique used in digital forensics to verify the **integrity of digital evidence**.

A reliable hash proves that the media content has **not been altered** during acquisition or analysis.

A hashing program generates a **fixed-length integer value** (hash value), typically ranging from **128 bits to 256 bits**, which uniquely represents the digital data on the seized media.

Even a **single-bit change** in the original evidence will result in a **completely different hash value**, making hashing a critical component of evidence validation.

---

## 2. Types of Hash Algorithms

Commonly used hash algorithms in digital forensics include:

- MD5 (Message Digest 5)
- SHA-1 (Secure Hash Algorithm 1)
- SHA-256 (Secure Hash Algorithm 256)

Note:
- MD5 and SHA-1 are faster but considered weaker
- SHA-256 is more secure and preferred in modern investigations

---

## 3. Hash Calculation Using HashCalc

HashCalc is a graphical tool used to calculate hash values of files.

### Activity: Hash Verification Using HashCalc

Steps:
1. Open HashCalc
2. Select the target file
3. Choose the hashing algorithm (MD5 / SHA-1 / SHA-256)
4. Generate the hash value
5. Record the hash value for verification

Purpose:
- To establish a baseline hash value before analysis
- To compare hash values after analysis or transfer

---

## 4. Hash Calculation Using Command Line (Windows)

Hash values can also be generated using the built-in Windows utility.

### Steps:
1. Open Command Prompt
2. Navigate to the file directory
3. Run the following command:

certutil -hashfile FileName

Or specify the algorithm:

certutil -hashfile FileName MD5  
certutil -hashfile FileName SHA1  
certutil -hashfile FileName SHA256  

The output hash value should be documented and preserved.

---

## 5. Forensic Duplication Process

Forensic duplication ensures that investigators work on a **copy of the evidence**, not the original media.

---

## 6. Disk Cloning

Disk Cloning is the process of copying the **entire contents of one hard drive to another hard drive**, including:

- Operating system
- Boot records
- System files
- User data
- Hidden and deleted data

A disk clone creates a **one-to-one replica** that can boot like the original drive.

Used when:
- Exact operational duplication is required
- System-level analysis is needed

---

## 7. Disk Imaging

Disk Imaging is the process of creating an **archival or backup image file** of an entire hard drive.

A disk image:
- Is stored as a single or segmented file
- Contains all data from the source drive
- Preserves file system structure and metadata

Used when:
- Evidence must be stored securely
- Analysis is performed on image files
- Long-term preservation is required

---

## 8. Types of Duplication Processes

### Hardware-Based Duplication
- Disk Cloning
- Disk Imaging

### Software-Based Duplication
- Disk Imaging only

Hardware-based methods are generally faster and more secure, while software-based methods are more flexible.

---

## 9. Concept of Write Blocker

A Write Blocker is a forensic tool that allows **read-only access** to a storage device.

Purpose:
- Prevents modification of original evidence
- Maintains evidence integrity
- Ensures chain of custody is not compromised

Write blockers are mandatory in forensic acquisition whenever possible.

---

## 10. Forensic Imaging Tools

### Software-Based Imagers
- FTK Imager
- EnCase Imager

### Hardware-Based Imagers
- MediaClone
- Image Master Solo 4

These tools are used to acquire forensic images while calculating hash values during acquisition.

---

## 11. Assignments / Practical Exercises

### Assignment 1: Hash Integrity Test
1. Create a demo file
2. Calculate and note the hash value
3. Change file access time or modify file content
4. Recalculate the hash value
5. Observe and document the hash mismatch

Purpose:
- To understand how file changes affect hash values

---

### Assignment 2: Forensic Imaging Validation
1. Create a disk or file image using FTK Imager
2. Generate hash values during imaging
3. Verify the image hash using HashCalc
4. Compare and confirm that both hash values match

Purpose:
- To validate forensic imaging accuracy

---
## 📘 MODULE 3 – Computer Forensics

---

## 1. Role of Computer in Crime & Misconduct

A computer can play different roles in cyber crimes and investigations:

### Computer as a Target
- Used to attack victim computers
- Attacks on Confidentiality, Integrity, and Availability (CIA) of information systems
- Examples: hacking, malware infection, DoS/DDoS attacks

### Computer as a Tool
- Used to commit crimes
- Examples:
  - Online fraud
  - Child pornography
  - Privacy violations
  - Cyber harassment and stalking

### Computer as an Accomplice
- Stores or processes key evidence
- Examples:
  - Personal information
  - Logs
  - Documents
  - Emails
  - Browsing history

---

## 2. File Systems in Different Operating Systems

### Windows
- FAT12
- FAT16
- FAT32
- NTFS

### Linux
- EXT2
- EXT3
- EXT4

### macOS
- HFS
- HFS+

Understanding file systems is essential for data recovery and artifact analysis.

---

## 3. Basics of Storage Media

### Types of Hard Drives

#### HDD (Hard Disk Drive)
Interfaces:
- IDE / ATA / PATA
- SATA
- SCSI

Hard Disk Components:
- Read / Write Heads
- Data Platters
- Spindle
- Actuator Arm
- Head Disk Assembly
- Landing Zone
- Landing Tray
- Debris Filter
- Scoring Damage Area

Definition:
A hard disk is a storage device that stores large amounts of data on magnetically charged platters and provides relatively fast access.

---

#### ATA (Advanced Technology Attachment)
- Older interface
- Low cost
- Limited speed and cable length
- Advantages and disadvantages depend on use case

#### SATA (Serial ATA)
- Improved version of ATA
- Faster data transfer
- Better cable management
- Widely used in modern systems

#### SCSI
- Mostly used in servers and industrial systems
- High performance
- Expensive
- Rare in home computers

---

### SSD (Solid State Drive)

- Uses flash memory
- No moving parts
- Much faster than HDD
- More expensive per GB

Typical sizes:
- HDD: 500 GB – 1 TB (cheaper)
- SSD: 64 GB – 256 GB (costly, faster)

---

## 4. Disk Partition Style

Partitioning is the process of creating logical drives on a physical disk.

### Types of Partitions
- Primary Partition: Contains operating system
- Extended Partition: Used to store data

When initializing a new disk, the system asks to choose:

### MBR (Master Boot Record)
- Legacy partition style
- Boot sector located at beginning of disk
- Stores boot loader and partition information
- Limited to 2 TB disk size

### GPT (GUID Partition Table)
- Modern partition style
- Used with UEFI firmware
- Supports large disks
- More reliable than MBR

---

## 5. Operating System (OS)

An operating system manages hardware and software resources and provides services to applications.

### Tasks Performed by OS
- Process Management
- Drive Management
- Memory Management
- File System Management

### Types of OS
- Server OS
- Client OS

### OS Backend for Forensics
- Registry
- Log Interpretation
- Volatile Data (RAM)

---

## 6. File System Fundamentals

A file system stores, organizes, and manages data on storage devices.

Used by:
- Hard disks
- CD/DVD
- Flash drives
- Floppy disks

### Types of File Systems

#### Database File System
- Files identified by metadata
- Searchable using SQL or text queries

#### Special Purpose File System
- Created during runtime
- Used for inter-process communication
- Example (Linux): /proc file system

---

## 7. Windows File System

### FAT File Systems
- FAT12
- FAT16
- FAT32

### NTFS (New Technology File System)
- High performance
- Self-repairing
- Supports permissions, encryption, compression

#### Master File Table ($MFT)
- Core component of NTFS
- Stores records of every file and folder

### MFT Analysis
- $MFT can be converted to CSV
- MFT-to-CSV parsers are used for timeline analysis

### FAT32 vs NTFS
- FAT32: No permissions, limited file size
- NTFS: Secure, supports large files, journaling

---

## 8. Potential Digital Evidence Created by OS

- Deleted files
- Registry entries
- Browser artifacts
- Prefetch files
- Event logs
- LNK (shortcut) files
- Volatile memory data

---

## 9. Data Recovery Fundamentals

### Types of Deleted Data

a) Deleted – Possible  
b) Formatted – Possible  
c) Wiped – Not Possible  
d) Overwritten / Overlapping – Not Possible  

### Data Recovery Tools
- Windows File Recovery
- Recover My Files
- Recuva
- FTK Imager (also used for imaging)

---

## 10. File Signature Analysis

File signatures identify file types based on headers, not extensions.

- First few bytes define file type
- Used to detect disguised or tampered files

Example:
- .DOC expected to open with Microsoft Word

### Key Points
- First 4 bytes: Header
- Last bytes: Footer
- Changing file extension does not change signature

### Tool
- WinHex – Hexadecimal file analysis
- Hex signature references available online

Purpose:
- Detect hidden or renamed files
- Identify malicious or disguised data

---

## 11. File Structure

Every file consists of:
1. File Name
2. File Header / Footer
3. File Content

Investigators must analyze files as physical documents in an office investigation.

---

## 12. File Carving

File carving extracts files based on content rather than metadata.

- Uses headers and footers
- Works even if file system metadata is destroyed

### Hiding a File (Binary Copy Technique)

Condition:
- Hidden file must be smaller than carrier file

Command:
copy /b CarrierFile + HiddenFile OutputFile.extension

---

## 13. Windows Registry Fundamentals

The Windows Registry is a hierarchical database.

Structure:
- Subtrees
- Keys
- Subkeys
- Values

Access:
Win + R → regedit

Two Panels:
- Key Pane (Left)
- Value Pane (Right)

### Five Root Keys

HKEY_CLASSES_ROOT  
- File associations and COM objects  

HKEY_CURRENT_USER  
- Data of currently logged-in user  

HKEY_LOCAL_MACHINE  
- System-wide configuration  
- Subkeys: HARDWARE, SAM, SECURITY, SOFTWARE, SYSTEM  

HKEY_USERS  
- All user profiles  
- DEFAULT, SID, SID_CLASSES  

HKEY_CURRENT_CONFIG  
- Current hardware profile  

---

## 14. NTUSER.DAT

- Stores user-specific registry data
- Multiple users → multiple NTUSER.DAT files

### Opening NTUSER.DAT (Using YARU)
1. Run tool as Administrator
2. File → Open User Hive (Local)
3. Load NTUSER.DAT from:
   C:\Users\Username\
4. Accept and load hive

---

## 15. Registry Acquisition & Analysis (REGA Tool)

### Acquisition
Open REGA →  
File → Collect Registry Files → Live System →  
Select destination folder → Save registry copies

### Analysis
File → Registry Analysis →  
Set time zone → Fill case info →  
Select registry data folder

---

## 16. Important User-Specific Registry Paths

- Recent Files:
  NTUSER\Software\Microsoft\Windows\CurrentVersion\RecentDocs

- Open/Save History:
  NTUSER\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSaveMRU

- Last Used Program:
  NTUSER\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\LastVisitMRU

- Typed URLs:
  NTUSER\Software\Microsoft\Internet Explorer\TypedUrls

- URL Timestamp:
  NTUSER\Software\Microsoft\Internet Explorer\TypedUrlsTime

Reference:
https://github.com/Ahmed-AL-Maghraby/Windows-Registry-Analysis-Cheat-Sheet

---

## 17. Web Browser Artifacts

Browser artifacts include:
- Cache
- Cookies
- Bookmarks
- Browsing History

Chrome Path:
C:\Users\Username\AppData\Local\Google\Chrome\User Data

---

## 18. Browser Artifact Analysis

- Data stored in SQLite databases
- Tool: DB Browser for SQLite  
  https://sqlitebrowser.org/

- Unix timestamp conversion:
  https://www.epochconverter.com/

---

## 19. Automated Digital Forensics Analysis

Techniques:
- Data Recovery
- File Carving
- Signature Analysis
- Registry Analysis
- Browser Artifact Analysis

---

## 20. Autopsy Forensics Tool

Autopsy is an open-source automated forensic platform.

Features:
- GUI-based
- Plugin architecture (Java & Python)
- Supports NTFS, FAT, EXT, UFS
- Timeline analysis
- Keyword search
- Registry analysis
- Web artifacts
- Email analysis
- EXIF data
- Android data extraction

Download:
https://www.autopsy.com/

Basic Workflow:
Open Autopsy → New Case → Case Info →  
Add Data Source → Run Ingest Modules

---

## 21. Volatile Data Acquisition (RAM)

Using Autopsy:
- Open Autopsy
- Capture Memory
- Select destination folder
- Provide output file name
- Capture memory

---

## 22. Windows Log Interpretation

### Windows Event Logs

Categories:
- Application Logs
- Security Logs
- System Logs
- Setup Logs
- Forwarded Events

Event Viewer:
Windows Logs → Select category

Application and Service Logs:
- Admin
- Operational
- Analytic
- Debug

### Log File Locations

System:
%SystemRoot%\System32\Config\SysEvent.Evt

Application:
%SystemRoot%\System32\Config\AppEvent.Evt

Security:
%SystemRoot%\System32\Config\SecEvent.Evt

---

## 23. Linux Log Interpretation

Common Linux Log Files:

- /var/log/messages
- /var/log/auth.log
- /var/log/kern.log
- /var/log/cron.log
- /var/log/maillog
- /var/log/httpd.log
- /var/log/lighttpd.log
- /var/log/boot.log
- /var/log/mysqld.log
- /var/log/utmp
- /var/log/wtmp
- /var/log/yum.log
- /var/log/dmesg
- /var/log/dpkg.log

### Viewing Logs (GUI)
System Menu → Administration → System Logs

---

## Assignments

Assignment 3 – Registry Artifact Analysis  
Assignment 4 – Browser Artifact Analysis  
Assignment 5 – Log File Analysis  

---
## 📘 MODULE 4 – Mobile Device Forensics

---

## 1. Features of Mobile Devices

Mobile device features are the set of capabilities and services provided by smartphones.

### 1. Display
- Screen size
- Resolution
- PPI (Pixels Per Inch)

---

### 2. Memory

Types of memory in mobile devices:

- **Internal Memory**  
  Built-in storage provided by the manufacturer.

- **Memory Card (SD Card)**  
  External removable storage.

- **Cloud Storage**  
  Online storage provided to prevent data loss if the device is lost or damaged.

#### Flash Memory Types

- **NAND Flash Memory**
  - Accessed like block devices (similar to HDD)
  - Used for data storage

- **NOR Flash Memory**
  - Allows individual cell access
  - Behaves like ROM
  - Used for firmware and boot code

**NAND vs NOR Trade-off:**  
Both are used for different applications based on speed, cost, and reliability.

---

### 3. Hardware Components

- **Battery** – Power source
- **Processor (CPU)**  
  Acts as the brain of the device  
  Performance measured in clock cycles  
  Example: 1 GHz = 1 billion cycles per second

---

### 4. Software

Three major software components:

- **Operating System (OS)**  
  Controls device operations  
  Major OS:
  - Apple iOS
  - Google Android
  - Windows Phone
  - BlackBerry OS

- **App Store**  
  Used to download and install applications

- **Maps & GPS**  
  Built-in mapping services and GPS receivers

---

### 5. Connectivity

- Bluetooth
- Wi-Fi
- Mobile Hotspot

---

## 2. Identity Module Characteristics (SIM)

**SIM (Subscriber Identity Module)** is an integrated circuit that securely stores subscriber identity.

Stored Information:
- ICCID
- IMSI
- Authentication Key (Ki – 128-bit value)
- Location Area Identity (LAI)
- SMS and Contacts

SIM Formats:
- Mini SIM
- Micro SIM
- Nano SIM
- Embedded SIM (eSIM)

---

## 3. Mobile Forensics Process Models

### Model A – Traditional Approach
- SMS
- Call Logs
- Events
- Emails
- Images and Videos

### Model B – Third-Party Applications
- WhatsApp
- Facebook
- Other social media apps

### Model C – Network Records
- CDR (Call Data Records)
- IPDR (IP Data Records)

---

## 4. Mobile Device Artifacts

Common mobile forensic artifacts include:
- Location information
- Subscriber and device details
- Date and time
- Language settings
- Phonebook
- Call logs
- SMS / MMS
- Multimedia files
- Emails
- Web browsing data
- Documents (PDF, DOC, PPT)
- User-created files and folders

---

## 5. SOP for Handling Mobile Device at Crime Scene

- Isolate the device immediately
- Prevent incoming calls, messages, or remote wipe
- Use **Faraday Bags**
- Use RF shielding cloths
- Avoid device becoming PIN-locked
- Maintain chain of custody

---

## 6. Mobile Device Extraction Techniques

### Logical Analysis
- Uses standard PC-to-mobile communication protocols
- Extracts existing data only

### Physical Analysis
- Direct memory access
- Extracts existing and deleted data

Methods:
- Micro Read
- Chip-Off

---

## 7. Mobile Device Extraction Types

### Logical Extraction
- Manual extraction
- File system analysis
- Existing data only

Important Android Paths:
- `/data/data/` – User application data
- `/mnt/asec/` – Unencrypted application containers

---

### Physical Extraction
- Micro Read
- Chip-Off
- Includes deleted data

---

## 8. Mobile Phone Analysis (Android APK Analysis)

Source Code Analysis Steps:
1. Copy APK file
2. Rename `.apk` to `.zip`
3. Extract contents
4. Files will be in `.dex` or `.class` format
5. Convert using:
   - dex2jar
   - JD-GUI
6. Analyze Java-readable source code

---

## 9. Android Rooting Concepts

Rooting provides superuser (administrator) access.

### Rooting Types

- **Temporary Root**
  - Root disabled after reboot

- **Permanent Root**
  - Root persists after reboot
  - Usually with custom ROM

- **Recovery Mode Root**
  - Root access only in recovery mode

---

## 10. Android Data Extraction Techniques (ADB)

**ADB (Android Debug Bridge)** is a critical mobile forensic tool.

Basic Commands:
- `adb devices` – List connected devices
- `ls` – List files
- `rm gesture.key` – Remove lock pattern
- `rm password.db` – Remove password
- `touch gesture.key` – Create new key

If ADB issues occur:
- `adb kill-server`

Create Backup:
- `adb backup -all backup.ab`

---

### USB Debugging

Enable:
Applications → Development → USB Debugging

- Starts ADB daemon
- Without root: limited access
- With root: full access
- Locked device → extraction becomes difficult

Convert Backup:
- Use **eSF Unpack Tar** to convert `.ab` to `.tar`

---

## 11. SQLite Database Analysis

- Lightweight open-source relational database
- Stored as a single file
- Common path:
  `/data/data/<package_name>/databases/`

Contains:
- Messages
- Contacts
- App data
- User activity

SQLite databases can be opened using SQLite viewers and SQL commands.

---

## 12. Dmesg Analysis

- Kernel message buffer
- May reveal keystroke logging or suspicious activity

Commands:
- `dmesg`
- `dmesg | wc`
- `dmesg | wc -l`
- `dmesg > dmesg.log`

Root not required, USB debugging sufficient.

---

## 13. Automated Android Forensics

Popular tools:
- Autopsy
- MOBILedit

### MOBILedit Workflow
1. Start MOBILedit
2. Phone → Cable Connection
3. Backup Settings
4. Select destination folder

Note:
- Install mobile drivers
- Use MOBILedit driver package

---

### Autopsy (Android Analysis)

Steps:
- Start Autopsy
- Create new case
- Add data source
- Select Android Analyzer
- Run ingest modules

---

## 14. iOS Overview

- Closed-source OS by Apple
- Strong security architecture
- Sandbox model:
  - Each app has its own directory
  - Cannot access other apps' data

---

## 15. iOS Security Overview

- System Architecture
- Encryption & Data Protection
- Network Security
- Device Access Control

---

## 16. iOS Jailbreaking

Jailbreaking allows administrative access.

Example Tool:
- Cydia

### Pros
- Customization
- Advanced tweaks
- Improved functionality

### Cons
- Piracy risk
- Security vulnerabilities
- Untrusted apps
- System instability
- No official updates

---

## 17. iOS Data Extraction Techniques

### iOS Backup Types
1. Computer Backup
2. Password-Protected Backup
3. iCloud Backup

Backup Location (Windows):
`AppData\Roaming\Apple Computer\MobileSync`

Open `Info.plist` using a plist viewer.

---

## 18. Important iOS Artifacts

- SMS – `sms.db`
- Contacts – `AddressBook.sqlitedb`
- Calendar – `Calendar.sqlitedb`
- Reminders – `reminders.db`
- Notes – `NoteStore.sqlite`
- Call History – `CallHistory.storedata`
- Voicemail – `voicemail.db`
- Safari History – `History.db`
- Safari Bookmarks – `Bookmarks.db`
- Locations – `consolidated.db`
- Photos Metadata – `Photos.sqlite`
- WhatsApp – `ChatStorage.sqlite`

---

## Assignments

Assignment 6 – Android Logical Extraction  
Assignment 7 – SQLite Database Analysis  
Assignment 8 – iOS Backup Artifact Analysis  

---
MODULE – 5 : EMAIL ANALYSIS FORENSICS
---

1. INTRODUCTION TO EMAIL FORENSICS
---------------------------------
Email Forensics deals with the identification, acquisition, analysis, and reporting
of email-related digital evidence for legal and investigative purposes.

• Layer 3 (Network Layer) and Layer 4 (Transport Layer) play a major role in
  network forensics and email communication analysis.

Email (Electronic Mail):
• A method of sending digital messages over computer networks.
• Faster than traditional postal services.
• Allows instant replies and attachments.

--------------------------------------------------

2. TYPES OF EMAIL SYSTEMS
------------------------

A. Webmail
• Emails accessed via a web browser.
• Examples: Gmail, Yahoo Mail, Hotmail

Advantages:
• Accessible from anywhere
• No local installation required

Major Problems:
• Security risks (phishing, spoofing)
• Advertisements
• Limited storage (free accounts)

--------------------------------------------------

B. Email Client
• Software installed on a computer to send/receive emails.

Examples:
• Outlook Express
• Microsoft Outlook
• Mozilla Thunderbird

Advantages:
• Offline access
• Better organization

Major Problems:
• System updates required
• Difficult to sync across multiple devices
• Backup responsibility lies with user

--------------------------------------------------

3. MAIL SERVER ARCHITECTURE
--------------------------

Mail Server:
• A computer system that works as a virtual post office.
• Handles sending, receiving, and storing emails.

Email Flow:
Sender
→ Sender Mail Client
→ Sender Mail Server
→ Recipient Mail Server
→ Recipient Mail Client / Webmail

--------------------------------------------------

4. EMAIL PROTOCOLS
-----------------

SMTP (Simple Mail Transfer Protocol)
• Used for sending emails.
• Handles outbound emails.
• Works between:
  - Mail User Agent (MUA)
  - Mail Transfer Agent (MTA)
  - Mail Delivery Agent (MDA)

--------------------------------------------------

IMAP (Internet Message Access Protocol v4)
• Used to retrieve emails.
• Emails remain on server.
• Supports multiple device access.
• Ideal for forensic investigations (data preserved).

--------------------------------------------------

POP3 (Post Office Protocol v3)
• Used to retrieve emails from mail server.
• Downloads emails to local machine.
• Usually deletes emails from server.
• Not ideal for forensic analysis due to data loss.

--------------------------------------------------

5. EMAIL HEADER ACQUISITION & ANALYSIS (WEBMAIL)
-----------------------------------------------

A. Acquisition Process
• Open the email
• Select “Show Original” or “View Source”
• Copy complete raw header data
• Paste into a text file
• Save the file securely
• Generate hash value using HashCalc
• Preserve hash for evidence integrity

--------------------------------------------------

B. Analysis Process
• Use online header analysis tools
• Steps:
  - Paste raw header
  - Analyze routing path
  - Extract:
    • Sender IP address
    • Mail server details
    • Domain name
    • Service provider
    • Timestamp

Useful Tool:
• MXToolbox – Email Header Analyzer
  https://mxtoolbox.com/EmailHeaders.aspx

--------------------------------------------------

6. EMAIL AUTHENTICATION MECHANISMS
---------------------------------

DMARC (Domain-based Message Authentication, Reporting & Conformance)
• Protects domains from email spoofing
• Defines how receivers handle failed SPF/DKIM checks
• Provides reporting to domain owners

--------------------------------------------------

SPF (Sender Policy Framework)
• Prevents unauthorized mail servers from sending emails
• Domain publishes a list of allowed mail servers
• Checked via DNS records

--------------------------------------------------

DKIM (DomainKeys Identified Mail)
• Uses digital signatures
• Signature stored in email header
• Ensures message integrity and authenticity

--------------------------------------------------

7. IP ADDRESS ANALYSIS
---------------------

• Extract IP address from email header
• Use IP lookup services to gather:
  - Country
  - ISP
  - Approximate location
  - Organization

Common Method:
• Google → “IP Lookup”
• Paste IP address
• Analyze results

--------------------------------------------------

8. FAKE EMAIL TOOLS (AWARENESS)
------------------------------
• Emkei’s Fake Mailer can be used to send spoofed emails
• Used for learning how spoofing works
• Important for understanding email fraud techniques

--------------------------------------------------

9. EMAIL CLIENT CONFIGURATION (FORENSIC USE)
--------------------------------------------

Mozilla Thunderbird:
• Free and open-source
• Cross-platform
• Supports POP3, IMAP, SMTP
• Stores emails locally (useful for forensic analysis)

Installation (Linux):
• Using Package Manager
• Using CLI (YUM / APT depending on distro)

--------------------------------------------------

10. IP TRACKING & TRACING TECHNIQUES
-----------------------------------

Tracking Links:
• Create a tracking URL
• Send to suspect
• Capture:
  - IP address
  - Browser
  - OS
  - Location

Popular Tools:
• Grabify – URL IP Logger
• IP Logger – Advanced tracking features

NOTE:
Use only for educational and authorized investigations.

--------------------------------------------------

11. ROLE OF SERVICE PROVIDERS IN EMAIL FORENSICS
------------------------------------------------

Information from ISPs:
• Username
• Phone number
• Personal details
• IP usage logs (day-wise)
• Physical address linked to IP

--------------------------------------------------

Google Account Data:
• Google Activity History
• Login timestamps
• Device information

--------------------------------------------------

Information from Mobile Service Providers:
• Customer registration forms
• Call records
• SMS logs
• Roaming details
• Cell tower location
• Tower dump data

Useful Codes:
*#*#4636#*#*
*#*#3646#*#*

Cell Tower Identification:
• MCC
• MNC
• LAC
• Cell ID

--------------------------------------------------

Information from Social Media Platforms:
• Dedicated Law Enforcement Request Portals
• User activity logs
• IP login history

--------------------------------------------------

Information from Domain Hosting Providers:
• Domain registration details
• Access logs
• FTP logs
• Payment records
• Website owner details
• Web developer information

--------------------------------------------------

12. EMAIL BEST PRACTICES (SECURITY AWARENESS)
--------------------------------------------

• Open emails only from known senders
• Verify physical address and phone number
• Avoid suspicious subject lines
• Never download executable attachments:
  .exe, .bat, .reg, .scr, .dll, .pif

--------------------------------------------------

13. ATTACHMENT MALWARE ANALYSIS
-------------------------------

Virus Scanning:
• Use VirusTotal
• Upload attachment
• Analyze results from multiple antivirus engines

--------------------------------------------------

14. DISPOSABLE EMAIL SERVICES
-----------------------------
• Temporary email services for testing
• Example: 10 Minute Mail
• Useful for investigations and privacy

--------------------------------------------------

15. PASSWORD MANAGEMENT
-----------------------

Best Practices:
• Length is more important than complexity
• Use passphrases
• Avoid reuse of passwords

Recommended Tool:
KeePass – Secure password manager

---
MODULE – 6 : OSINT (OPEN SOURCE INTELLIGENCE)
---

1. INTRODUCTION TO OSINT
-----------------------
OSINT (Open Source Intelligence) refers to intelligence collected from
publicly available sources.

• Not related to open-source software
• Not classified or secret intelligence
• Collected legally from open/public sources

OSINT Sources Include:
• Text-based information
• Images
• Videos
• Webinars
• Public speeches
• Social media
• Forums
• Websites
• Public records

--------------------------------------------------

2. TYPES OF OSINT
----------------

Offensive OSINT:
• Information gathering before an attack
• Used by attackers, red teams, penetration testers
• Focus on reconnaissance

Defensive OSINT:
• Used to learn about attacks against an organization
• Helps in threat intelligence and brand monitoring
• Used by blue teams and SOC analysts

--------------------------------------------------

3. OSINT TOOLS
--------------

ViewDNS.info
• Website offering multiple information-gathering tools
• Used to collect data about:
  - Domain
  - IP address
  - DNS records
  - Reverse IP lookup
  - WHOIS data

Website:
https://viewdns.info/

--------------------------------------------------

Wayback Machine
• Initiative of Internet Archive (501(c)(3) non-profit)
• Digital library of:
  - Archived websites
  - Old versions of webpages
• Useful for:
  - Website history
  - Deleted content
  - Evidence reconstruction

Related Projects:
• Open Library
• Archive-It

Website:
https://archive.org/web/

--------------------------------------------------

4. BROWSER & INTERNET PRIVACY
-----------------------------

Private Browsing:
• No browsing history saved locally
• Cookies/session data cleared after close
• Sessions are sandboxed

Limitations:
• Still visible to:
  - Search engines
  - ISPs
  - Network administrators

--------------------------------------------------

Important Privacy & OSINT Browser Tools:
• NoScript
• Adblock Plus
• Abine Blur
• Shodan
• ScamAdvisor
• CCleaner

--------------------------------------------------

DuckDuckGo:
• Zero data collection
• Less tracking
• Faster results
• Uses multiple search sources

Website:
https://duckduckgo.com/

--------------------------------------------------

KProxy:
• Free web proxy service
• Browsing via proxy server

Website:
https://www.kproxy.com/

--------------------------------------------------

OpenVPN:
• VPN solution
• Encrypts internet traffic
• Protects privacy

--------------------------------------------------

TOR Browser:
• Privacy-focused browser
• Routes traffic through TOR network
• Generates new circuit/session
• Used to access dark web (.onion)

--------------------------------------------------

5. DARK WEB MARKETS & SERVICES (EDUCATIONAL)
--------------------------------------------

The Hidden Wiki:
• Dark web version of Wikipedia
• Contains links and information for beginners

Onion Link:
http://zqktlwi4fecvo6ri.onion/

--------------------------------------------------

Dream Market:
• Anonymous marketplace
• Anonymous signup & payment
• One of the smaller onion markets

Onion Link:
http://lchudifyeqm4ldjj.onion/

--------------------------------------------------

The Hidden Wallet:
• Anonymous digital wallet
• Bitcoin-based transactions

Onion Link:
http://nql7pv7k32nnqor2.onion/

--------------------------------------------------

Facebook (Onion Service):
• Facebook has TOR onion address
• Claims no tracking (verification uncertain)

Onion Link:
https://www.facebookcorewwwi.onion/

--------------------------------------------------

Impreza Hosting:
• Anonymous & secure hosting
• Hidden service hosting on TOR
• Random .onion domain assigned
• Approx cost: $8/month

Onion Link:
http://imprezawcjntsdf2.onion/

--------------------------------------------------

6. FILE SHARING MODELS
---------------------

Client-Server Model:
• Client requests data from centralized server
• Examples: Web browsing, email

Peer-to-Peer (P2P):
• Decentralized file sharing
• Peers act as both client and server
• Software searches for other connected peers

--------------------------------------------------

7. OSINT FRAMEWORK
-----------------
Information gathering is time-consuming.
Security researchers documented OSINT tools to simplify investigations.

OSINT Framework:
• Categorized OSINT tools
• Covers domains, IPs, people, social media, malware, etc.

Website:
https://osintframework.com/

---
MODULE – 7 : NETWORK FORENSICS
---

1. INTRODUCTION TO NETWORK FORENSICS
-----------------------------------
Network Forensics involves monitoring, capturing, and analyzing
network traffic to detect and investigate incidents.

Network:
• Combination of two or more computers
• Used to share resources

Types of Networks:
• LAN – Local Area Network
• MAN – Metropolitan Area Network
• WAN – Wide Area Network
• CAN – Campus Area Network
• SAN – Storage Area Network
• HAN – Home Area Network

--------------------------------------------------

2. INTERNetwork
---------------
• Network of networks
• Uses TCP/IP protocol suite
• IP is the addressing protocol

--------------------------------------------------

3. OSI MODEL
------------

7. Application Layer
   - DNS, WWW, SMTP, FTP, POP

6. Presentation Layer
   - Data formatting, encryption
   - HTML, DOC, JPEG

5. Session Layer
   - Session establishment
   - TCP sessions, SIP, RTP, RPC

4. Transport Layer
   - End-to-end reliability
   - TCP, UDP, SCTP, SSL, TLS

3. Network Layer
   - Logical addressing
   - IP, ARP, ICMP, IGMP

2. Data Link Layer
   - Physical addressing
   - Ethernet, MAC, ATM, HDLC

1. Physical Layer
   - Media & signal transmission

--------------------------------------------------

4. ADDRESS MANAGEMENT
--------------------

Logical Addressing:
• IP Addressing

Physical Addressing:
• MAC Addressing

--------------------------------------------------

IP Address:
• Numerical label for devices
• Network ID + Host ID
• IPv4 / IPv6

Static IP:
• Does not change

Dynamic IP:
• Changes on each connection

Public IP:
• Internet-facing address

Private IP:
• Used inside private networks

--------------------------------------------------

MAC Address:
• Unique hardware identifier
• Assigned to network interface

--------------------------------------------------

5. PORTS & PROTOCOLS
-------------------

Ports:
• Range: 0 – 65535
• Open / Closed states

Protocols:
• FTP, DHCP, DNS, NFS
• SMTP, POP3
• HTTP, HTTPS

--------------------------------------------------

6. NETWORKING TOOLS
------------------

NirLauncher:
• Collection of 200+ portable tools
• No installation required
• Features:
  - Password recovery
  - Network monitoring
  - Browser data extraction
  - File searching

--------------------------------------------------

7. NETWORK DEVICES
-----------------
• Router
• Switch
• Firewall (Software / Hardware)

Firewall:
• Controls inbound/outbound traffic
• Can block specific ports

--------------------------------------------------

8. NETWORK SECURITY THREATS
--------------------------
• Network Sniffing
• IP Spoofing
• MAC Spoofing
• DoS / DDoS
• Man-in-the-Middle (MITM)
• Session Hijacking

--------------------------------------------------

9. NETWORK FORENSIC MODEL
------------------------
Plan → Protect → Detect → Respond

Plan:
• Traffic threat management
• Incident response preparation

Protect:
• Secure network architecture

Detect:
• Continuous network monitoring

Respond:
• Network forensic investigation

--------------------------------------------------

10. NETWORK TRAFFIC ACQUISITION
-------------------------------

Alert Data:
• Tool: Snort (IDS)

Full Content Data:
• Tool: Tcpdump

Session Data:
• Tools: Argus, SANCP, NetFlow

Statistical Data:
• Tools: tcpdstat, capinfos

--------------------------------------------------

11. PCAP ANALYSIS
----------------
• Wireshark
• Network Miner

WinPcap:
• Industry-standard packet capture
• Used in Windows environments

---
MODULE – 8 : MALWARE ANALYSIS
---


1. INTRODUCTION TO MALWARE
-------------------------
Malware:
• Software designed to harm:
  - Confidentiality
  - Integrity
  - Availability (CIA)

--------------------------------------------------

2. GOALS OF MALWARE ANALYSIS
---------------------------
• Identify malicious behavior
• Understand infection method
• Detect persistence mechanisms
• Create indicators of compromise (IOCs)

--------------------------------------------------

3. TYPES OF MALWARE ANALYSIS
---------------------------

Static Analysis:
• Analyzing malware without execution
• File structure, strings, headers

Dynamic Analysis:
• Executing malware in isolated environment
• Observing runtime behavior

Automated Analysis:
• Using sandbox platforms

--------------------------------------------------

4. WHAT IS ANALYZED
------------------
• Behavior Analysis
• Code-Based Analysis

--------------------------------------------------

5. AUTOMATED ANALYSIS
--------------------
Tools:
• VirusTotal
• Joe Sandbox

--------------------------------------------------

6. STATIC ANALYSIS
-----------------
Tool:
• PEStudio

--------------------------------------------------

7. BEHAVIOR-BASED ANALYSIS
-------------------------
• Observes malware activities
• Executed in sandbox environment

System-Based Analysis:
• Regshot (registry comparison)

Network-Based Analysis:
• Wireshark (traffic monitoring)

--------------------------------------------------

8. CODE-BASED ANALYSIS
---------------------
Reverse engineering malware internals

Tools:
• OllyDbg
• Hex Editor
• Decompiler
• Disassembler
• Debugger
