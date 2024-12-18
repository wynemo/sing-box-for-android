# SFA

Experimental Android client for sing-box, the universal proxy platform.

## how to compile

find a linux machine, use docker or podman, for example using podman:
`podman run --rm -it -v $PWD:/app -w /app fabernovel/android:api-31-gcloud-ndk-snapshot bash`

then in container:

```
wget -c https://go.dev/dl/go1.23.3.linux-amd64.tar.gz
rm -rf /usr/local/go && tar -C /usr/local -xzf go1.23.3.linux-amd64.tar.gz
export PATH=$PATH:/usr/local/go/bin
git clone https://github.com/SagerNet/sing-box.git
cd sing-box
make lib_install
export PATH=$PATH:/root/go/bin/
make lib_android
```

copy libbox.aar to sing-box-for-android/app/libs/

then in sing-box-for-android, compile:

`./gradlew :app:assembleDebug`

## video link 视频讲解
[youtube视频 - sing-box 安卓汉化版 编译](https://www.youtube.com/watch?v=nf16ap-a3PI)
## Documentation

https://sing-box.sagernet.org/installation/clients/sfa/

## License

```
Copyright (C) 2022 by nekohasekai <contact-sagernet@sekai.icu>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <http://www.gnu.org/licenses/>.

In addition, no derivative work may use the name or imply association
with this application without prior consent.
```

Under the license, that forks of the app are not allowed to be listed on F-Droid or other app stores
under the original name.
