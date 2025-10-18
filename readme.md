# ACME Medical Center - USB Forensic Examination (Simulation)
### [PAPER APA FORMAT INVESTIGATION (Google Drive Link)](https://drive.google.com/file/d/1sooxEUYCWqaGKrWIftG_4F1VpfWroGha/view?usp=sharing)
*Completed: October 2, 2025*  
*Category: Digital Forensics & Incident Response (DFIR)*

- - -

## Overview
The purpose of this project is to simulate a **digital forensic investigation** using a confiscated USB drive from a fictional employee who was suspected of violating company policy at ACME Medical Center.

This project demonstrate **professional forensic methodology** including:
- Evidence acquisition and imaging  
- Hash verification for data integrity  
- Analysis using industry-standard tools *(FTK Imager, Autopsy, OSForensics)*  
- Structured documentation of findings *(view above Google Drive link)*

> ## ⚠️ **Disclaimer:**
>  ### All "contraband" are simply just **photos of cats.**   
> This investigation is entirely fictional and no real illegal material or sensitive data is used.  
> All names, files, and evidence are simulated replicas of a realistic forensic scenario and workflow.  

- - -

## Scenario
The ACME Medical Center security team confiscated a USB device from employee Joe Bob, who is suspected of viewing illegal material on company computers and drives. The ACME
Medical Center requests that all findings be documented in this report. The results of this analysis may be admissible in court proceedings.

### Flash Drive Setup:
The USB flash drive used for this examination was restored using OSForensics with an image called **"Furry Image"** which contained the contraband cat photos. This will act as our suspect drive.

<img width="778" height="460" alt="image" src="https://github.com/user-attachments/assets/e63cd3fe-ba1a-449a-a70e-670d2d7efeca" />

The newly restored suspect drive would never be opened directly to ensure integrity of the original evidence.

- - -

## Hardware and Software

### **Software:**  
| Tool | Version |
|------|----------|
| **USB Write Blocker ALL Windows** | v1.3 |
| **OSForensics** | 11.0.1007 |
| **FTK Imager** | 4.7.3.81 |
| **Autopsy** | 4.22.1 |

*All software used to conduct this examination is either owned or licensed to (me, my company,
etc) and has been fully tested and/or validated for usage.*


### **Hardware:**
| Component | Description |
|------------|-------------|
| Host Machine | Windows 10 |
| Processor | Intel Core i7-12700K @ 5.0 GHz |
| Evidence Device | JetFlash Transcend 8 GB USB |

- - -

# **Methodology**

## 1️⃣ Preparation:
  1. **Environment setup** - isolated from the internet, validate forensic tools, document environment, etc.
  2. Prepare storage media by labeling drive and **forensically erasing bit-by-bit** so all bits are set to zeroes.
  3. Fill out a **chain of custody**.

**NOTE: Since this is a home lab and simulation, I did not conduct these steps. In a real world scernario, I would be forced to.
These steps are extremely important to ensuring an investigation protects evidence integrity, credibility, and legal defensiiblity.**

- - -

## 2️⃣ Hardware Inspection
I received the USB drive (Transcend 8 GB, USB_SERIAL_REDACTED) at **11:21 AM EST**. The drive does not appear to have its connections or external casing damaged. I photographed and documented before imaging.

### *Appendix A: Suspect USB Inspection Photos*

<img width="635" height="436" alt="image" src="https://github.com/user-attachments/assets/7a9ee8f3-3634-466c-9956-3d8799f4b253" />

- - -

## 3️⃣ Forensic Imaging
1. To begin, I software blocked the suspect USB using the company-approved **USB Write Blocker ALL Windows v1.3** and then **verified the hash of the original suspect USB with OSForensics**.  

<img width="530" height="648" alt="Screenshot 2025-10-02 124203" src="https://github.com/user-attachments/assets/e66990f9-ea1b-4c12-8cc6-6eef022931f9" />

2. I then created **two identical forensic images** in FTK Imager, one as a **forensic copy** *(Suspect USB FURRY IMAGE drive.001)* and then a **forensic working copy** *(Suspect FURRY IMAGE Forensic Working copy.001)*.
   
*The forensic copy was used to conduct the research, discover evidence, and analyze data.* 

3. FTK imager provided the MD5 and SHA-1 hash values for each copy. I compared them to the original drive.   
The hash values matched the original drive and one another, verifying that the data was not damaged, overwritten, or altered in any way during the image process.  

<img width="568" height="455" alt="Screenshot 2025-10-02 120920" src="https://github.com/user-attachments/assets/c69d4bf9-6dca-4078-838c-3305276a275c" />
<img width="615" height="486" alt="Screenshot 2025-10-02 131854" src="https://github.com/user-attachments/assets/ca90e625-d636-4b27-8f04-dd92925a2705" />

- - -

## 4️⃣ Investigation Findings

I used the **FTK Imager** to conduct an investigation into the forensic working copy. I added the image file as evidence, which showcased many folders for potential evidence on **partition 1**.
The main folder was called **“Harmless Folder”** containing subfolders listed as **Videos** and **HighQuality**. There was also a **Pictures folder** and **‘Secret Folder’**.

<img width="879" height="389" alt="Screenshot 2025-10-02 135701" src="https://github.com/user-attachments/assets/c1eba984-4096-4daa-b41c-9d56d2df4b75" />

Illegal images and videos were located under **"Harmless Folder"**. It contained a subfolder **“Video”** containing **49 graphics of .jpg, .mov, and .m4v files**, all of which contain illegal material (photos of cats). There were **6 videos** total of cats. 

The root directory itself contained an **additional 51 similarly formatted image files** and **12 videos**, though they are all either corrupted or overwritten. The video titles referenced cats and kittens. 

I used **Autopsy** to recover a deleted backup folder that appeared twice labeled **"HighQuality"** which contained **82 images of cats**. Before deletion, it would've been located under "Harmless Folder" and root.  

The files were exported to the examiner’s machine to a folder located in the FTK Images folder called “Exported Contents” with their associated file extensions. ***See Appendix B for extracted images.***

### *Appendix B: Images*

<img width="493" height="217" alt="image" src="https://github.com/user-attachments/assets/b16e953b-9c2f-4fef-93c7-104a157db21a" />

Exported Files Locations

<img width="1997" height="449" alt="Screenshot 2025-10-02 155322" src="https://github.com/user-attachments/assets/5d1d7285-a3b9-4b0a-a657-9a23a208620c" />
<img width="2393" height="573" alt="Screenshot 2025-10-02 155142" src="https://github.com/user-attachments/assets/915a4ce1-61bc-4197-bdad-565606d6cd76" />

For a DFIR report, the blurred photo **would** be used to avoid breaking laws and chain-of-custody rules.
The second, unblurred photo **would NOT** be used for the DFIR report.

- - -

## 5️⃣ Final Hash Values

The SHA-1 and MD5 hash values were verified to ensure that data integrity was maintained.  
I used FTK Imager to verify its image post-analysis, with the result matching the pre-analysis hash values.  

### *Appendix C: Hash Values*

<img width="761" height="372" alt="image" src="https://github.com/user-attachments/assets/b5199b38-e1e4-40fe-86d1-d44daf32b76b" />

- - -

## Findings (Simulated)

After conducting a thorough investigation into the provided USB drive, I determined it contains potential illegal images. 
Despite some files being overwritten and corrupted, there is more than enough evidence to support the criminality of the contents of Joe Bob’s drive. 
A total of 149 confirmed photos of illegal content were located. Due to the explicit nature of the images recovered, the photos and drive will be turned into law enforcement for further investigation.

- - -

## Conclusion
This project demonstrates the **complete forensic workflow**, from securing evidence with proper handling to analysis and documentation.  
Despite this case being completely fictional, it reflects **industry-standard DFIR methodology** used in real investigations.  

### Skills Demonstrated:
- Digital evidence imaging and verification (MD5/SHA-1)  
- Chain-of-custody documentation  
- Use of FTK Imager, Autopsy, and OSForensics  
- Forensic workflow and methodology  
- Technical report writing and structured documentation  
- File recovery and metadata analysis  

- - -

## Tags
`Digital Forensics` · `Incident Response` · `Cybersecurity` · `Autopsy` · `FTK Imager`

- - -
