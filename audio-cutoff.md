# Jamesdsp / Pipewire randomly cut off / crackling
This happened to me on freshly install Fedora 43 with updated 6.17.7 kernel

1. Copy /usr/share/pipewire/pipewire.conf to /etc/pipewire/pipewire.conf
And then edit these into the copied file
```
    default.clock.quantum       = 2048 #1024
    default.clock.min-quantum   = 1024 #32
    default.clock.max-quantum   = 4096 #2048
```
> [!WARNING]
> Be warned, that those lines prevent underruns by highering the output latency alot. 
https://github.com/Audio4Linux/JDSP4Linux/issues/47#issuecomment-2565036420

2. Install realtime-setup and add your account into realtime group with

```sudo usermod -aG realtime <user>```
