# Final Year Project

This is an object detection project.

## How to install

Create a virtual environment

```bash
python3 -m venv venv
```

Source the virtual environment

```bash
source venv/bin/activate
```

Install the requirements

```bash
pip install -r requirements.txt

```

## How to run on webcam

Run the webcam project

```bash
python detect.py --weights weights/best.pt --source 0 --conf 0.3
```

## Run from Drone Camera

```bash
v4l2-ctl --list-devices
```

First setup streaming

```bash
cvlc -vvv v4l2:///dev/video4 --sout '#standard{access=http,mux=ogg,dst=localhost:8080}'
```

```bash
python detect.py --source http://localhost:8080 --weights weights/best.pt
```
