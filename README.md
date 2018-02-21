# qtqr
Fork of official *ppa:qtqr* with support for v4l2loopback.

Add this to **qtqr.py**, on line 797, at the end of the function`def getVideoDevices(self):`

Before `if __name__ == '__main__':`
```
else:
            file_names = [x for x in os.listdir("/dev") if x.startswith("video")]
            file_names.sort()
            for file_name in file_names:
                     yield([
                        ("Webcam input from " + file_name),
                        os.path.join("/dev", file_name)
                    ])
```
