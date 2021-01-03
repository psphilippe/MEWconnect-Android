# MEWconnect-Android
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fpsphilippe%2FMEWconnect-Android.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2Fpsphilippe%2FMEWconnect-Android?ref=badge_shield)


Android Version of the MEWconnect Applicaiton

## Getting Started

This project is built using Android studio, you can also use docker to build the project

### Build with docker

Make sure you have docker installed

```
docker build -t android-build .
docker run --rm -v "$PWD":/home/gradle/ -w /home/gradle/ android-build gradle assemble
docker run --rm -v "$PWD":/home/gradle/ -w /home/gradle/ android-build zipalign -p 4 app/build/outputs/apk/release/app-release-unsigned.apk release/MEWconnect-Android-$RELEASE-unsigned.apk
docker run --rm -v "$PWD":/home/gradle/ -w /home/gradle/ android-build apksigner sign --out release/MEWconnect-Android-$RELEASE.apk --ks MEWconnect-keystore.jks --ks-key-alias mewconnect --ks-pass env:KEYSTORE_PASS --key-pass env:KEY_PASS release/MEWconnect-Android-$RELEASE-unsigned.apk
```


## License
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fpsphilippe%2FMEWconnect-Android.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2Fpsphilippe%2FMEWconnect-Android?ref=badge_large)