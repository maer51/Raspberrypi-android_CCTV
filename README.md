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

## 포트포워딩 설정
### **1. 공유기 설정으로 들어간다**
<img width="436" alt="fort1" src="https://user-images.githubusercontent.com/115002427/196354828-c7fe2ecb-1cb7-4602-9433-6ed0a5bbb373.png">

### **2. DDNS설정을 연다 <br/> (호스트이름을 정하고 사용자ID는 이메일을 써야한다) <br/> (정상 등록이라고 뜨면 성공)**
<img width="438" alt="fort2" src="https://user-images.githubusercontent.com/115002427/196365513-33d22cb7-98b9-4fa4-966c-c497c0b74da1.png">

### **3. 포트포워딩 설정으로 들어간다** <br/> (내부 ip주소에는 라즈베리파이에 ip주소를 넣는다) <br/> (외부포트는 만번대 숫자 아무거나 넣고 내부포트에는 8081를 넣는다)
<img width="437" alt="fort3" src="https://user-images.githubusercontent.com/115002427/196369955-6433f1ff-1793-49b7-b69b-44cf0ac4be18.png">

### **4. 코드에 ip주소 부분에 DDNS주소를 넣는다** <br/> (String url = "http://DDNS주소:8081/";
<img width="387" alt="20221018_165503" src="https://user-images.githubusercontent.com/115002427/196370747-d314ae88-aee8-4dbf-bd18-16e9c3ad5a33.png">

## 사용 시
<img src="https://user-images.githubusercontent.com/115002427/196373968-070464eb-8a69-45f0-9a35-a38aaf4b6997.jpg" width=270 height=480>








