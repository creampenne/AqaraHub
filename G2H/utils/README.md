# [Aqara] 스마트 홈카메라 허브 G2H (CH-H01)

Lumi United Technology CO., Ltd

1. busybox-armv7l

   busybox

2. h264grabber

   스트리밍

3. imggrabber

   스냅샷

4. rRTSPServer

   프레임 오류 발생

5. hostname

   SD Card 삽입 후 부팅시 TELNET 활성화 (UART 연결 불필요)

6. rtsp_start_g2h.sh

   G2H 전용 RTSP 실행(영구) 쉘 스클립트

   h264grabber, rRTSPServer -> /system/bin  
   rtsp_start.sh -> /etc/initd.d/S90app

   - rtsp://[IP]/ch0_0.h264 (고해상도)
   - rtsp://[IP]/ch0_1.h264 (저해상도)

고해상도

```shell
   h264grabber -f &
   rRTSPServer &
```

저해상도

```shell
   h264grabber -f -r low &
   rRTSPServer -r low &
```
