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
   
   4). fix sdk/android_gradle/webrtc/CMakeList.txt:    (optional?).
   
   ${WEBRTC_REPO}/${WEBRTC_BUILD_DIR}/gen/logging/rtc_event_log/*.cc

   5). copy sdk/libs/ffmpeg from webrtc_android.
   

* update gradle.properties in sdk/android_gradle/ 

* gn gen out/android_debug_arm --args='target_os="android" target_cpu="arm"' 

* ninja -C out/android_debug_arm network_tester_config_proto_gen 


* How to apply patch in git?

First the stats:

git apply --stat a_file.patch

Then a dry run to detect errors:

git apply --check a_file.patch

Finally, you can use git am to apply your patch as a commit: it allows you to sign off an applied patch.

This can be useful for later reference.

git am --signoff < a_file.patch 
