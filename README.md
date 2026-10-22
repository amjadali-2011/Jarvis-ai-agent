# JARVIS Desktop AI

A modular desktop AI assistant built with Python and PyQt6. The project is designed around a desktop HUD, voice interaction, optional provider integrations, automation actions, and plugins.

> **Project status:** Work in progress. Features depend on the installed optional packages, operating system, provider configuration, and API access. Test actions carefully before relying on them.

## Features

- PyQt6 desktop HUD and assistant interface
- Compact Mini Mode intended for quick access while using other windows
- Voice input/output and model-provider configuration
- Modular actions and plugin loading
- Desktop, browser, file, system-monitoring, and media utilities (availability varies by platform)
- Optional remote dashboard components

## Requirements

- Python 3.10 or newer recommended
- Windows 10/11, with some features requiring Windows-specific packages; macOS/Linux support varies by action
- Internet connection for online model providers and related services
- A supported model provider/API credential if you choose a hosted AI provider

## Quick start (Windows)

1. Install Python from https://www.python.org/downloads/. During installation, enable **Add Python to PATH**.
2. Download or clone this repository.
3. Open Command Prompt in the project folder.
4. Create and activate a virtual environment:

   ```bat
   py -m venv .venv
   .venv\Scripts\activate
   ```

5. Update pip and install dependencies:

   ```bat
   python -m pip install --upgrade pip
   pip install -r requirements.txt
   ```

6. Follow the in-app provider/engine settings to configure your chosen AI provider. Do not commit API keys or private configuration.
7. Start the application:

   ```bat
   python main.py
   ```

If the project includes a maintained Windows launcher, you may also try `run.bat` after installing dependencies.

## Mini Mode

Use the Mini Mode control in the HUD to switch to a compact floating assistant. The mini window is intended to remain accessible while you work in another application. Use the restore/open-HUD control to return to the main interface. Window behavior can vary by desktop environment.

## Configuration and privacy

- Keep API keys, OAuth credentials, tokens, and private settings outside version control.
- Review any automation action before enabling it: actions that control your computer may open apps, interact with windows, or change files.
- Grant only the permissions needed for the features you use.
- Do not run untrusted plugins. Inspect plugin source code first.
- Avoid storing passwords or sensitive personal data in assistant memory.
- Hosted AI providers may process prompts according to their own policies; review the provider terms before sending private information.

## Troubleshooting

### `python` or `py` is not recognized
Reinstall Python and enable **Add Python to PATH**, then reopen Command Prompt.

### Missing module error
Activate the virtual environment and run:

```bat
pip install -r requirements.txt
```

### Microphone/audio problems
Check Windows microphone permissions and the selected input/output device. Close other apps that may exclusively use the audio device.

### Provider connection or API errors
Check your network, provider settings, API key, quota, and model availability. Never paste secret keys into public issues.

### Browser automation does not work
Install Playwright browser binaries if the feature requires them:

```bat
python -m playwright install
```

### A feature is unavailable
Some integrations have optional dependencies or operating-system limitations. Check the comments in `requirements.txt` and the relevant module before troubleshooting.

## Development checklist

- [ ] Test startup on a clean virtual environment
- [ ] Verify Mini Mode entry, drag, always-on-top behavior, and restore
- [ ] Test voice input/output and provider errors
- [ ] Test each computer-control action safely
- [ ] Review plugin permissions and secret handling
- [ ] Run syntax checks and smoke tests on the target OS

## Repository layout

The application uses a modular structure with the main entry point, PyQt6 UI, action modules, core helpers, memory/configuration modules, and plugins. Exact modules may evolve as the project is updated.

## Contributing

1. Fork the repository or create a feature branch.
2. Make focused changes and describe the reason for each change.
3. Run syntax checks and test the affected feature.
4. Update documentation and requirements when behavior changes.
5. Open a pull request with test results and known limitations.

## License

See the `LICENSE` file if included in the repository. Do not assume permissions beyond those granted by that license.

## Disclaimer

This is a personal/experimental desktop assistant. Automation can affect your files, applications, and system settings. Back up important data and supervise actions, especially when testing computer-control features.
