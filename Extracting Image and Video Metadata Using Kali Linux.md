# Digital-Footprint-Investigation
Extracting Image and Video Metadata Using Kali Linux

## 1.0 Introduction
Metadata is data that provides information about other data. Digital files such as images, videos, and documents contain hidden metadata that stores information about the file's creation, modification, device used, location, and technical characteristics.
Metadata analysis is important in cybersecurity and digital forensics because it helps investigators trace the origin of files, verify authenticity, and identify potential privacy risks associated with digital footprints.

### Project Directory Structure
Below is the organizational structure of this repository, showing the designated folders for images, video assets, and report logs:
* `Extracting Image and Video Metadata Using Kali Linux.md` (Main Lab Report)
* `img/` — Contains all analyzed JPEG files
* `videos/` — Contains the MP4 video used for metadata analysis
* `files/` — Contains TXT files and integrity logs
* `screenshot/` -Contains the screenshots of the installation and version of the Exiftool

## 2.0 Installation of Exiftool
Run the following commands on the kali linux to install the Exiftool as shown below

sudo apt update
sudo apt install libimage-exiftool-perl
![Digital Footprint Investigation](screenshot/screen1.png)


To verify the version run exiftool -ver
![Digital Footprint Investigation](screenshot/screen2.png)

## 3.0 Image analysis
The following information contains a detailed analysis from two images. 
Two JPEG images were analyzed using ExifTool to extract hidden metadata layers.
### image one
* **Command Used:** `exiftool image1.jpeg`
  ![Digital Footprint Investigation](img/image1.png)

### image two
* **Command Used:** `exiftool image2.jpeg`
  ![Digital Footprint Investigation](img/image2.png)
## 4.0 PNG analysis
Unlike JPEGs, PNG files handle metadata differently and often store textual chunks (like software names) rather than extensive camera details. One PNG image was analyzed.

### png image 
* **Command Used:** `exiftool image3.png`
  ![Digital Footprint Investigation](img/image3(1).png)


## 5.0 GPS investigation
Geotagging embeds Exchangeable Image File Format (EXIF) data containing latitude and longitude coordinates directly into an image when taken on GPS-enabled devices. This information is also available in the Metadata.
* **Command Used:** `exiftool -gps:all photo1.jpeg`
  ![Digital Footprint Investigation](img/photo1.png)


## 6.0 Video analysis
An MP4 video file from the `videos/` directory was analyzed to identify container-specific metadata such as structural codecs, duration, and track modifications.

* **Command Used:** `exiftool sample_video.mp4`
  ![Digital Footprint Investigation](videos/sample_video.png)

 ## 7.0 Reflection 
The extraction of metadata highlights severe security and privacy implications for individuals and organizations alike. Unintentionally publishing geotagged images exposes physical locations, daily routines, and home addresses to malicious actors, facilitating targeted social engineering or physical tracking. 

From an enterprise standpoint, metadata leakage can inadvertently expose internal directory structures, usernames, software versions, and corporate network configurations. For defensive security practitioners, enforcing automated metadata stripping policies on public-facing platforms is an absolute necessity to prevent open-source intelligence (OSINT) exploitation.
