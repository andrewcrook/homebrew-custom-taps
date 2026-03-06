# Andrew's Custom Homebrew Formulas

## Setup

```bash
> brew tap andrewcrook/custom-taps
> brew install andrewcrook/custom-taps/<formula-name>
```

## Patched from homebrew-core

- ~~**nmap@7.95** Downgrade from v7.97 due to error running with `sudo` and `/dev/bpf`~~
  - [issue #3127](https://github.com/nmap/nmap/issues/3127)
- ~~**pluseaudio** - v17.0 with patch to fix modules on MacOS `.so -> .dylib`~~
- **Logitech Options+** Custom removed AI,autoupdate (I used brew) and stop calling home. 

## Notes

- ~~**nmap@7.95** Downgrade from v7.97 due to error running with `sudo` and `/dev/bpf`~~ 
  - How I added to this tap:
  ```bash
  >  brew tap andrewcrook/custom-taps
  >  brew tap homebrew/core --force
  >  brew uninstall nmap
  >  brew extract --version=7.95 nmap andrewcrook/custom-taps
  >  brew install nmap@7.95
  >  brew pin  nmap@7.95
  ```
- ~~**pluseaudio** - v17.0 with patch to fix modules on MacOS. Pulseaudio versions => 17.0.1 should fix the issues. (tested on MacOS 14.6.1)~~
  - **Note**: Add the following to allow TCP connections and adjust as required or look up instructions for adding security. I personally use this setup locally rather than over external networks.

 ```bash
  add
  load-module module-native-protocol-tcp auth-ip-acl=127.0.0.1;10.211.55.2 auth-anonymous=1
  to
  /opt/homebrew/opt/pulseaudio/etc/pulse/default.pa
  ```
