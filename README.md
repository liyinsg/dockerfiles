# Dockerfiles
Automated Docker Builds

## webrtc-android
Build Android apprtc application
```
docker run --rm -v $HOME/webrtc:/home/build/webrtc -v $HOME/.ccache:/home/build/.ccache liyin/webrtc-android
```
