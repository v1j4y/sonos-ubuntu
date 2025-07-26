Simple steps to stream audio to sonos on ubuntu 20.04
=====================================================

1. Download noson-app

```bash
sudo add-apt-repository ppa:jlbarriere68/noson-app
sudo apt-get update
sudo apt-get install noson-app
```

2. Dependencies
```bash
sudo apt install pavucontrol
```

3. Setup pulseaudio
```bash
systemctl --user unmask pulseaudio.{service,socket} --now
systemctl --user start pulseaudio
```

4. Start noson server to stream to sonos device
```bash
noson-app -cli
connect ${SONOS_SPEAKER_NAME)
playpulse
```

5. Set default output `pacmd` & `pavucontrol`
  ```bash
  pacmd list-sinks
  ```
 - should show `noson-cli` as sink

 - start gui using
  ```bash
  pavucontrol
  ```

  - select noson as sink.

6. Play music

7. profit !
