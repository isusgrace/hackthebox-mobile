Hi, Can you speak Thai ?

Yes, I can speak Thai.

มา วันนี้เราจะมาทำข้อ Don't Overreact หมวด Mobile ระดับ Very easy

Step 1 สร้าง Directory และนำเข้าไฟล์
```
mkdir <new directory>
```
ใช้คำสั่ง mkdir ใช้สำหรับสร้างไดเรกทอรี (หรือโฟลเดอร์) ใหม่บนระบบไฟล์
```
cd <new directory>
```
ตามด้วย คำสั่ง cd ใช้สำหรับเปลี่ยนไดเรกทอรีหรือโฟลเดอร์ปัจจุบันในเทอร์มินัล

ตามด้วย คำสั่ง mv ใช้ในการย้ายหรือเปลี่ยนชื่อไฟล์และไดเร็กทอรี ในที่นี้เราจะใช้คำสั่ง mv ในการย้ายไฟล์

```
┌──(kali㉿kali)-[~/Downloads]
└─$ mkdir isusgrace03

┌──(kali㉿kali)-[~/Downloads]
└─$ cd isusgrace03

┌──(kali㉿kali)-[~/Downloads]
└─$ mv ~/Downloads/'Don t Overreact.zip' /home/kali/Downloads/isusgrace03/
```

Step 2 unzip
```
unzip 'Don t Overreact.zip'
```
คำสั่ง unzip ใช้สำหรับแตกไฟล์ที่ถูกบีบอัดในรูปแบบ .zip เพื่อดึงไฟล์และโฟลเดอร์ทั้งหมดออกมาจากไฟล์เก็บถาวรนั้น (ไฟล์ที่เราเลือกจะแตก)
```
┌──(kali㉿kali)-[~/Downloads/isusgrace03]
└─$ unzip 'Don t Overreact.zip'
Archive:  Don t Overreact.zip
[Don t Overreact.zip] app-release.apk password: 
replace app-release.apk? [y]es, [n]o, [A]ll, [N]one, [r]ename: A
  inflating: app-release.apk
```
นี่คือสิ่งที่ได้หลังจากเราทำการแตกไฟล์ .zip
```
┌──(kali㉿kali)-[~/Downloads/isusgrace03]
└─$ ls
 app-release.apk  'Don t Overreact.zip'
```
คำสั่ง ls ใช้แสดงรายการไฟล์และไดเรกทอรีที่มีอยู่ในไดเรกทอรีปัจจุบัน เมื่อ ls จะได้ไฟล์ทั้งหมด 2 ไฟล์

Step 3 apktoool
```
apktool d <file.apk>
```
คำสั่ง apktool ใช้สำหรับทำวิศวกรรมย้อนกลับไฟล์ APK โดยมีหน้าที่ถอดรหัสไฟล์ APK ออกเป็นส่วนประกอบต่างๆ เพื่อให้สามารถดูและแก้ไขทรัพยากรภายใน เช่น ไฟล์ XML, รูปภาพ, และโค้ดภาษา Smali จากนั้นจึงสามารถประกอบกลับเป็นไฟล์ APK ใหม่หลังจากการแก้ไขได้
```
┌──(kali㉿kali)-[~/Downloads/isusgrace03]
└─$ apktool d app-release.apk
I: Using Apktool 2.7.0-dirty on app-release.apk
I: Loading resource table...
I: Decoding AndroidManifest.xml with resources...
I: Loading resource table from file: /home/kali/.local/share/apktool/framework/1.apk
I: Regular manifest package...
I: Decoding file-resources...
I: Decoding values */* XMLs...
I: Baksmaling classes.dex...
I: Copying assets and libs...
I: Copying unknown files...
I: Copying original files...
```
นี่คือสิ่งที่ได้หลังจากใช้คำสั่ง apktool 
```
┌──(kali㉿kali)-[~/Downloads/isusgrace03]
└─$ ls
 app-release   app-release.apk  'Don t Overreact.zip'
```
คำสั่ง ls ใช้แสดงรายการไฟล์และไดเรกทอรีที่มีอยู่ในไดเรกทอรีปัจจุบัน เมื่อ ls จะได้ไฟล์ทั้งหมด 2 ไฟล์ (ไฟล์ที่มีอยู่ก่อนหน้านี้) และได้ไดเรกทอรีมา 1 ไดเรกทอรี คือ app-release

Step 4 app-releas
```
┌──(kali㉿kali)-[~/Downloads/isusgrace03]
└─$ cd app-release
```
คำสั่ง cd ใช้สำหรับเปลี่ยนไดเรกทอรีหรือโฟลเดอร์ปัจจุบันในเทอร์มินัล ในส่วนนี้เราต้องการดูว่าในไดเรกทอรี app-release มีไฟล์หรือไดเรกทอรีอะไรบ้าง
```
┌──(kali㉿kali)-[~/Downloads/isusgrace03/app-release]
└─$ ls -la
total 40
drwxrwxr-x   8 kali kali 4096 Oct 22 22:30 .
drwxrwxr-x   4 kali kali 4096 Oct 22 22:30 ..
-rw-rw-r--   1 kali kali 1163 Oct 22 22:30 AndroidManifest.xml
-rw-rw-r--   1 kali kali 1953 Oct 22 22:30 apktool.yml
drwxrwxr-x   2 kali kali 4096 Oct 22 22:30 assets
drwxrwxr-x   6 kali kali 4096 Oct 22 22:30 lib
drwxrwxr-x   3 kali kali 4096 Oct 22 22:30 original
drwxrwxr-x 131 kali kali 4096 Oct 22 22:30 res
drwxrwxr-x  10 kali kali 4096 Oct 22 22:30 smali
drwxrwxr-x   3 kali kali 4096 Oct 22 22:30 unknown
```
คำสั่ง ls ใช้แสดงรายการไฟล์และไดเร็กทอรีที่มีอยู่ในไดเร็กทอรีปัจจุบัน

คำสั่ง -l ออปชันนี้สั่งให้ ls แสดงผลในรูปแบบ "ยาว" (Long Listing Format) ซึ่งจะให้ข้อมูลรายละเอียดของไฟล์แต่ละไฟล์ดังนี้

- สิทธิ์ — เช่น drwxr-xr-x 

  ตัวแรกระบุชนิดไฟล์: d = directory, - = regular file, l = symlink

  ตัวต่อมาแบ่งเป็น 3 ชุด แต่ละชุด r=read w=write x=execute

- จำนวนลิงก์ — จำนวน hard links

- เจ้าของไฟล์ — ชื่อผู้ใช้ที่เป็นเจ้าของไฟล์

- กลุ่ม — ชื่อกลุ่มของไฟล์

- ขนาดไฟล์ — ขนาดเป็น bytes

- วันที่และเวลา — วันที่และเวลาที่มีการแก้ไขไฟล์ล่าสุด

- ชื่อไฟล์/ไดเร็กทอรี — ชื่อจริงของไฟล์หรือไดเร็กทอรี
หลังจากใช้คำสั่ง ls -la เราจะพบไดเรกทอรี 6 ไดเรกทอรี คือ assets, lib, original, res, smali และ unknown
นอกจากนี้ เราจะพบไฟล์อีก 2 ไฟล์ คือ AndroidManifest.xml และ apktool.yml

Step 5 grep
```
┌──(kali㉿kali)-[~/Downloads/isusgrace03/app-release]
└─$ grep -ir 'hackthebox'
assets/index.android.bundle:__d(function(g,r,i,a,m,e,d){Object.defineProperty(e,"__esModule",{value:!0}),e.myConfig=void 0;var t={importantData:"baNaNa".toLowerCase(),apiUrl:'https://www.hackthebox.eu/',debug:'SFRCezIzbTQxbl9jNDFtXzRuZF9kMG43XzB2MzIyMzRjN30='};e.myConfig=t},400,[]);
```
คำสั่ง grep ใช้สำหรับค้นหารูปแบบข้อความหรือสตริงที่กำหนดภายในไฟล์ข้อความหนึ่งไฟล์หรือหลายไฟล์ และแสดงบรรทัดที่พบรูปแบบนั้น ๆ ออกมา
```
SFRCezIzbTQxbl9jNDFtXzRuZF9kMG43XzB2MzIyMzRjN30=
```
นี่คือข้อความที่น่าสนใจ มันคือ flag ที่ถูกเข้ารหัสด้วย Base64
<img width="1920" height="1080" alt="C1" src="https://github.com/user-attachments/assets/c788c583-bc80-47f7-b3b7-e0f0b88ea3f0" />
เราสามารถถอดรหัสได้โดยการใช้ CyberChef 
```
echo "SFRCezIzbTQxbl9jNDFtXzRuZF9kMG43XzB2MzIyMzRjN30=" | base64 -d
```
หรือใช้คำสั่ง echo บน kali linux
```
┌──(kali㉿kali)-[~/Downloads/isusgrace03/app-release]
└─$ echo "SFRCezIzbTQxbl9jNDFtXzRuZF9kMG43XzB2MzIyMzRjN30=" | base64 -d
HTB{XXXXX}
```
นี่คือสิ่งที่ได้

XXXXX ไม่ใช้ flag นะ คือปิดไว้ จะได้ทำเอง

เพิ่มเติม
```
echo -n "ข้อความของคุณ" | base64
```
คำสั่งนี้ใช้สำหรับเข้ารหัสข้อความด้วย Base64
```
echo "ข้อความของคุณ" | base64 -d
```
คำสั่งนี้ใช้สำหรับถอดรหัสข้อความที่ถูกเข้ารหัสด้วย Base64
