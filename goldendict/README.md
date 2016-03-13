# Dockerfiles
Automated Docker Builds

## goldendict
Build goldendict
```sh
git clone https://github.com/goldendict/goldendict $HOME/src/goldendict
docker run --rm -v $HOME/src/goldendict:/home/build/src liyin/goldendict
```
