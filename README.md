# Andrews Custom Homebrew Formulas

## Patched from homebrew-core

- **pluseaudio** - v17.0 with patch to fix modules on MacOS. Pulseaudio versions => 17.0.1 should fix the issues. (tested on MacOS 14.6.1)
    - **Note**: Add the following to allow TCP connections and adjust as required or look up instructions for adding security. I personally use this setup locally rather than over external networks.


  ```bash
  add 
  load-module module-native-protocol-tcp auth-ip-acl=127.0.0.1;10.211.55.2 auth-anonymous=1 
  to 
  /opt/homebrew/opt/pulseaudio/etc/pulse/default.pa
  ```

*This Repo is a mirror from my private Git server it updates automatically every 8 hours*
