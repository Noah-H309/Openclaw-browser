## How to enable browser tool in OpenClaw AI assistant

This tool opens a Chrome/Brave/Edge/Chromium window and navigates to the URL that you instruct AI model to go. It is quite useful e.g. 'play a relaxing Youtube video', but it is disabled by default. It works better than Brave embedded AI tool, though it still needs improvement.

In order to enable it:

1. Shutdown openclaw-gateway completely
2. Backup openclaw.json file, usually found in folder: <br>

**Windows:** users/'yourname'/.openclaw/openclaw.json <br>

**Mac:**  ~/.openclaw <br>

**Linux:** home/user/.openclaw

3. Replace in openclaw.json

**only these lines**

```json
"plugins": {
    "entries": {
      "ollama": {
        "enabled": true
```
      
**with these lines**

```json
"plugins": {
    "allow": [
      "ollama",
      "browser",
      "memory-core"
    ],
    "entries": {
      "browser": {
        "enabled": true
      },
      "ollama": {
        "enabled": true
```

4. Relaunch with shell command: ollama launch openclaw
5. Run in another shell: openclaw browser --browser-profile openclaw start
5. Enjoy automatic browsing experience!!
