# Dockerfiles
Automated Docker Builds

## webrtc-android
Build Android apprtc application
```sh
docker run --rm -v $HOME/webrtc:/home/build/webrtc -v $HOME/.ccache:/home/build/.ccache liyin/webrtc-android
```
