# Jamesdsp / Pipewire randomly cut off / crackling
 System Info:
 - Distro: Fedora Linux 42 (KDE Plasma Desktop Edition)
 - Kernel: 6.17.7

## Fix:
### Step 1:
Copy /usr/share/pipewire/pipewire.conf to /etc/pipewire/pipewire.conf

And then edit these into the copied file
```
    default.clock.quantum       = 2048 #1024
    default.clock.min-quantum   = 1024 #32
    default.clock.max-quantum   = 4096 #2048
```
> [!WARNING]
> Be warned, that those lines prevent underruns by highering the output latency alot. 
https://github.com/Audio4Linux/JDSP4Linux/issues/47#issuecomment-2565036420

### Step 2:
Install realtime-setup and add your user into realtime group with:
```sudo usermod -aG realtime <user>```
