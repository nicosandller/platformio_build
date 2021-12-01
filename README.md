# PlatformIO image

This is a Dockerfile packaging PlatformIO Core. The image contains the PlatformIO Command Line Interface for developing software for embedded devices and IoT projects. To speedup development.

This image is specifically for `gcp cloud build` for continuous development.

## cloudbuild.yaml
```
steps:
- name: 'nicosandller/platformio-build:latest'  
  dir: .
  args: ['run']   

artifacts: 
  objects: 
    location: 'gs://BUCKET_ID/'
    paths: ['/workspace/.pio/build/esp32/firmware.bin']
```
