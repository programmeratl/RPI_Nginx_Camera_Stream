# RPI_Nginx_Camera_Stream
Stream USB camera from RPI to Nginx
(1)Nginx Installation on Ubuntu 16 or 18 64 bit version.
	Please check Nginx.txt for instructions. We have compiled Nginx with RTMP, HLS and VOD modules.

(2)Prepare RPI:
	(2.1) Install brew.
	(2.2) Install Cmake version 3.16.5. Reference http://osdevlab.blogspot.com/2015/12/how-to-install-latest-cmake-for.html but download version https://github.com/Kitware/CMake/releases/download/v3.16.5/cmake-3.16.5.tar.gz
	(2.3) Install Docker. Ref: https://dev.to/rohansawant/installing-docker-and-docker-compose-on-the-raspberry-pi-in-5-simple-steps-3mgl .
	(2.4) Install FFMPEG.
	(2.5) For webcam ffmpeg api please follow instructions from: https://github.com/jkuri/ffmpeg-webcam-rtmp-stream

	#After all set up get in folder 
	 cd /home/pi/ffmpeg-webcam-rtmp-stream  #your path might be different
	#and fire command
	 ./build/stream /dev/video10 rtmp://nginx_server_ip:1935/live/stream flv 800 600 24


(3)For playback:
	For playback side we are using video js free source player. Please fine attached videojs folder and set it up in your web server.
	You can replace IP of nginx server in index.html.
