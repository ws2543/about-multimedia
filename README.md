# about-multimedia
## 有关多媒体与直播

![](./doc/有关多媒体与直播.png)

## 多媒体知识

### RTSP+(RTCP/RTP)

1. 通过Wireshark截获VLC播放某厂摄像头RTSP流+(RTCP/RTP基于UDP)
- All Flows
  - ![](./doc/rtsp_rtcp_rtp.png)

- <details><summary>RTSP协议交互过程</summary>
    OPTIONS rtsp://115.236.15.165:554/cam/realmonitor?channel=1&subtype=0 RTSP/1.0
    CSeq: 2
    User-Agent: LibVLC/3.0.6 (LIVE555 Streaming Media v2016.11.28)

    RTSP/1.0 401 Unauthorized
    CSeq: 2
    WWW-Authenticate: Digest realm="Login to 4M0747EPAA1D284", nonce="745449738fdf77164f570c37c9186b52"

    OPTIONS rtsp://115.236.15.165:554/cam/realmonitor?channel=1&subtype=0 RTSP/1.0
    CSeq: 3
    Authorization: Digest username="admin", realm="Login to 4M0747EPAA1D284", nonce="745449738fdf77164f570c37c9186b52", uri="rtsp://115.236.15.165:554/cam/realmonitor?channel=1&subtype=0", response="d2bbade17fc39c7e39f7122862e7b781"
    User-Agent: LibVLC/3.0.6 (LIVE555 Streaming Media v2016.11.28)

    RTSP/1.0 200 OK
    CSeq: 3
    Server: Rtsp Server/3.0
    Public: OPTIONS, DESCRIBE, ANNOUNCE, SETUP, PLAY, RECORD, PAUSE, TEARDOWN, SET_PARAMETER, GET_PARAMETER

    DESCRIBE rtsp://115.236.15.165:554/cam/realmonitor?channel=1&subtype=0 RTSP/1.0
    CSeq: 4
    Authorization: Digest username="admin", realm="Login to 4M0747EPAA1D284", nonce="745449738fdf77164f570c37c9186b52", uri="rtsp://115.236.15.165:554/cam/realmonitor?channel=1&subtype=0", response="0c1a43aee144161f39c11b20c7ed37fa"
    User-Agent: LibVLC/3.0.6 (LIVE555 Streaming Media v2016.11.28)
    Accept: application/sdp

    RTSP/1.0 200 OK
    CSeq: 4
    x-Accept-Dynamic-Rate: 1
    Content-Base: rtsp://115.236.15.165:554/cam/realmonitor?channel=1&subtype=0/
    Cache-Control: must-revalidate
    Content-Length: 401
    Content-Type: application/sdp

    v=0
    o=- 2252091052 2252091052 IN IP4 0.0.0.0
    s=Media Server
    c=IN IP4 0.0.0.0
    t=0 0
    a=control:*
    a=packetization-supported:DH
    a=rtppayload-supported:DH
    a=range:npt=now-
    m=video 0 RTP/AVP 96
    a=control:trackID=0
    a=framerate:25.000000
    a=rtpmap:96 H264/90000
    a=fmtp:96 packetization-mode=1;profile-level-id=4D002A;sprop-parameter-sets=Z00AKp2oHgCJ+WbgICAoAAAfQAAGGoQgAA==,aO48gAA=
    a=recvonly
    SETUP rtsp://115.236.15.165:554/cam/realmonitor?channel=1&subtype=0/trackID=0 RTSP/1.0
    CSeq: 5
    Authorization: Digest username="admin", realm="Login to 4M0747EPAA1D284", nonce="745449738fdf77164f570c37c9186b52", uri="rtsp://115.236.15.165:554/cam/realmonitor?channel=1&subtype=0/", response="5f799cb37a51a1463224540af4db9ac5"
    User-Agent: LibVLC/3.0.6 (LIVE555 Streaming Media v2016.11.28)
    Transport: RTP/AVP;unicast;client_port=61246-61247

    RTSP/1.0 200 OK
    CSeq: 5
    Session: 272327472040;timeout=60
    Transport: RTP/AVP/UDP;unicast;client_port=61246-61247;server_port=41490-41491;ssrc=039FB573
    x-Dynamic-Rate: 1

    PLAY rtsp://115.236.15.165:554/cam/realmonitor?channel=1&subtype=0/ RTSP/1.0
    CSeq: 6
    Authorization: Digest username="admin", realm="Login to 4M0747EPAA1D284", nonce="745449738fdf77164f570c37c9186b52", uri="rtsp://115.236.15.165:554/cam/realmonitor?channel=1&subtype=0/", response="5411553c7eb81bdbe384bac58407863b"
    User-Agent: LibVLC/3.0.6 (LIVE555 Streaming Media v2016.11.28)
    Session: 272327472040
    Range: npt=0.000-

    RTSP/1.0 200 OK
    CSeq: 6
    Session: 272327472040
    Range: npt=0.000000-
    RTP-Info: url=trackID=0;seq=9513;rtptime=2160343659

    TEARDOWN rtsp://115.236.15.165:554/cam/realmonitor?channel=1&subtype=0/ RTSP/1.0
    CSeq: 7
    Authorization: Digest username="admin", realm="Login to 4M0747EPAA1D284", nonce="745449738fdf77164f570c37c9186b52", uri="rtsp://115.236.15.165:554/cam/realmonitor?channel=1&subtype=0/", response="12056f94551c6675cc80cc18df1f0fd5"
    User-Agent: LibVLC/3.0.6 (LIVE555 Streaming Media v2016.11.28)
    Session: 272327472040

    RTSP/1.0 200 OK
    CSeq: 7
    Session: 272327472040
</details>


## 直播技术和SRS开源直播平台

![](./doc/推流和拉流.jpg)

![](./doc/HLS方案模拟.jpg)

![](./doc/RTMPvsHLSvsHTTPFLV.png)

![](./doc/产品比较.png)

![](./doc/核心功能对比.png)

![](./doc/网络协议对比.png)

![](./doc/体系结构对比.png)

![](./doc/安装部署对比.png)

![](./doc/code对比.png)

![](./doc/cdn友好性对比.png)

## 有关Nginx高性能服务器

![](./doc/有关Nginx.png)


## 资料汇总
1. [RTMP WIKI](https://en.wikipedia.org/wiki/Real-Time_Messaging_Protocol)
2. [rtmp specification v1.0](http://wwwimages.adobe.com/www.adobe.com/content/dam/acom/en/devnet/rtmp/pdf/rtmp_specification_1.0.pdf)
3. [HLS WIKI](https://en.wikipedia.org/wiki/HTTP_Live_Streaming)
4. [rfc8216 - HTTP Live Streaming](https://tools.ietf.org/html/rfc8216)
5. [北京大学，视频编码算法研究室](http://vcl.idm.pku.edu.cn/articlesList.html?tag=research&page=0)
6. [流媒体加密](https://github.com/gwuhaolin/blog/issues/10)
7. [使用flv.js做直播](https://github.com/gwuhaolin/blog/issues/3)
8. [雷霄骅 - RGB、YUV像素数据处理](https://blog.csdn.net/leixiaohua1020/article/details/50534150)
9. [雷霄骅 - H.264视频码流解析](https://blog.csdn.net/leixiaohua1020/article/details/50534369) 
10. [雷霄骅 - h264_analysis](https://github.com/leixiaohua1020/h264_analysis)
11. [雷霄骅 - PCM音频采样数据处理](https://blog.csdn.net/leixiaohua1020/article/details/50534316)
12. [雷霄骅 - AAC音频码流解析](https://blog.csdn.net/leixiaohua1020/article/details/50535042)
13. [雷霄骅 - FLV封装格式解析](https://blog.csdn.net/leixiaohua1020/article/details/50535082)
14. [雷霄骅 - UDP-RTP协议解析](https://blog.csdn.net/leixiaohua1020/article/details/50535230)
