* https://webrtc.googlesource.com/src/+/refs/heads/master/docs/native-code/android/index.md 

* fetch --nohooks webrtc_android

   gclient sync

* source activate python2

* Checkout #30432:  be99ee8f17f93e06c81e3deb4897dfa8253d3211

* Comment out src/third_party/ijar/BUILD.gn
  
	 if (is_linux | …) {
	
  }

* Apply patches

   1). frameworks
   
   2). fix GN build error
   
   3). add android_gradler
   
   4). add sdk/libs/ffmpeg
   
   5). fix sdk/android_gradle/webrtc/CMakeList.txt:    
   
   ${WEBRTC_REPO}/${WEBRTC_BUILD_DIR}/gen/logging/rtc_event_log/*.cc

