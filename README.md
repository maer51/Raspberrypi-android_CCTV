# Raspberrypi-android CCTV
라즈베리파이 카메라 영상을 핸드폰에서 실시간으로 보여주는 CCTV앱

## 사용한 도구 
* Android Studio (Java)
* Webview API
* Raspberrypi
* (Raspberrypi camera) or usb (camera)

## 주요 기능
* Raspberrypi 카메라 영상을 실시간으로 보여준다



## 라즈베리파이 설정
### **1. 라즈베리파이**를 실행시킵니다.
  <img src="https://user-images.githubusercontent.com/115002427/195792397-722c4985-2eac-47b8-9b6f-3680c1059179.png">
  
### **2. 터미널**을 실행시킵니다.
  <img src="https://user-images.githubusercontent.com/115002427/195792432-672d5b6e-d85a-4142-a109-a240c46832fc.png">
  
### **3. motion** 설치 (sudo apt-get install motion)
  <img src="https://user-images.githubusercontent.com/115002427/195795292-af345ace-511f-4256-9ffd-de976e8a12ca.png">
  
### **4. 웹캠 인식** 확인 (lsusb)
  <img src="https://user-images.githubusercontent.com/115002427/195797072-d54fa386-cd75-40ff-ad88-d9921181d307.png">
  
### **5. motion** 설정 (sudo nano /etc/motion/motion.conf)
  <img src="https://user-images.githubusercontent.com/115002427/195800383-ef3258c1-f585-4a4a-bc13-51ff510e8235.png">
  <img src="https://user-images.githubusercontent.com/115002427/195801274-7efdb2dc-cfab-4202-8703-984a7910d376.png" width=583 height=391>
  
  <table>
  <tr>
     <td><b>5-1. daemon off → on</b></td>
     <td><b>5-2. Ctrl + w, width 검색</b></td>
  </tr>
  <tr>
    <td><img src="https://user-images.githubusercontent.com/115002427/195804393-e4373d1f-4f44-42ae-bb3b-19dc1c149161.png" width=370 height=530></td>
    <td><img src="https://user-images.githubusercontent.com/115002427/196334092-0d2f9a64-c986-4303-afba-499d967cc9ae.png" width=370 height=530></td>
  </tr>
 </table>
 
 <table>
  <tr>
     <td><b>5-3. width 640, height 480  (해상도 설정)</b></td>
     <td><b>5-4. framerate 100   (프레임 설정)</b></td>
  </tr>
  <tr>
    <td><img src="https://user-images.githubusercontent.com/115002427/196335771-424895f9-10d6-4e73-b82e-74ca6f18c478.png" width=370 height=530></td>
    <td><img src="https://user-images.githubusercontent.com/115002427/196336020-e33c51d1-7357-4b9f-af35-6def0915813b.png" width=370 height=530></td>
  </tr>
 </table>
 
 <table>
  <tr>
     <td><b>5-5. stream_maxrate 검색 후 stream_maxrate 100 <br/> (최대 프레임 설정)</b></td>
     <td><b>5-6. webcontrol_localhost 검색 후 <br/> webcontrol_localhost off <br/> (프레임 설정)</b></td>
  </tr>
  <tr>
    <td><img src="https://user-images.githubusercontent.com/115002427/196338350-ea35a262-7049-41f5-ab45-83c3277c83d7.png" width=370 height=530></td>
    <td><img src="https://user-images.githubusercontent.com/115002427/196338517-3c68df34-9c5a-4528-ac59-e8b70ff62f9e.png" width=370 height=530></td>
  </tr>
 </table>
 
### **6. motion 서비스** 등록 (sudo nano /etc/default/motion)
  <img src="https://user-images.githubusercontent.com/115002427/196339113-43cf0d60-52f2-420f-abe9-517cf5e499f7.png">

<table>
  <tr>
     <td><b>6-1. start_motion_daemon=yes   (백그라운드 설정)</b></td>
  </tr>
  <tr>
    <td><img src="https://user-images.githubusercontent.com/115002427/196339543-30eda902-4fb9-4773-ac93-1ce97b12edc0.png" width=570 height=370></td>
  </tr>
 </table>
 
### **7. motion 자동실행** 설정 (sudo nano /etc/rc.local)
  <img src="https://user-images.githubusercontent.com/115002427/196340235-8e9fc805-c8d3-4945-ad97-45df98995569.png">

<table>
  <tr>
     <td><b>7-1. sudo motion 추가 </b></td>
  </tr>
  <tr>
    <td><img src="https://user-images.githubusercontent.com/115002427/196340511-6333fdb7-b975-4923-87ac-4787f1c86746.png" width=570 height=370></td>
  </tr>
 </table>

### **8. motion 폴더권한** 설정 (sudo chmod 777 /var/lib/motion)
  <img src="https://user-images.githubusercontent.com/115002427/196341647-85dba6ab-d383-46ad-b16e-b297a01ccf68.png">






