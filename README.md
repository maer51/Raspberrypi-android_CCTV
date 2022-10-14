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
1. **라즈베리파이**를 실행시킵니다.
  <br/><img src="https://user-images.githubusercontent.com/115002427/195792397-722c4985-2eac-47b8-9b6f-3680c1059179.png">
2. **터미널**을 실행시킵니다.
  <br/><img src="https://user-images.githubusercontent.com/115002427/195792432-672d5b6e-d85a-4142-a109-a240c46832fc.png">
3. **motion** 설치 (sudo apt-get install motion)
  <br/><img src="https://user-images.githubusercontent.com/115002427/195795292-af345ace-511f-4256-9ffd-de976e8a12ca.png">
4. **웹캠 인식** 확인 (lsusb)
  <br/><img src="https://user-images.githubusercontent.com/115002427/195797072-d54fa386-cd75-40ff-ad88-d9921181d307.png">
5. **motion** 설정 (sudo nano /etc/motion/motion.conf)
  <br/><img src="https://user-images.githubusercontent.com/115002427/195800383-ef3258c1-f585-4a4a-bc13-51ff510e8235.png">
  <br/><img src="https://user-images.githubusercontent.com/115002427/195801274-7efdb2dc-cfab-4202-8703-984a7910d376.png"width=583 height=391>











