# Contributing to SmartHome

Thank you for considering a contribution. Help is welcome with bug reports, feature proposals, code, tests, documentation, reviews, and helping other users. Please read the [Code of Conduct](CODE_OF_CONDUCT.md); participation in this project is subject to it.

## Contents

- [Before you start](#before-you-start)
- [Report a bug or request a feature](#report-a-bug-or-request-a-feature)
- [Development setup](#development-setup)
- [Development workflow](#development-workflow)
- [Code, tests, and commits](#code-tests-and-commits)
- [Pull requests](#pull-requests)
- [License](#license)

## Before you start

Search [existing issues](https://github.com/trankhahao7/SmartHome/issues) and pull requests before opening a new one. The repository has `good first issue` and `help wanted` labels; check whether an issue is still open and relevant before working on it. There is no published assignment or stale-issue policy, so ask in the issue before investing in a substantial change.

For a new feature, behavior change, or broad refactor, open an issue first to discuss the problem and proposed scope. Small fixes and documentation corrections can usually proceed directly to a pull request. Use GitHub Issues for project questions and proposals; the `question` label is available. Do not assume a separate Discussions or chat channel is available.

## Report a bug or request a feature

- For bugs, use the [bug report form](https://github.com/trankhahao7/SmartHome/issues/new?template=bug_report.yml). Include the affected component, project version or commit, environment, steps to reproduce, expected and actual behavior, and relevant sanitized logs.
- For feature requests, search for a related issue first, then open an issue describing the problem, who it affects, the proposed solution, alternatives, and how the idea fits this project's local smart-home scope.
- Do not post security vulnerabilities in public issues, pull requests, or discussions. Follow [SECURITY.md](SECURITY.md) to report them privately.

Remove passwords, tokens, Wi-Fi credentials, private network details, and personal information from logs and screenshots before sharing them.

## Development setup

SmartHome contains a Flutter client, a Python/FastAPI server, and Arduino firmware for ESP32. See the root [README](README.md) for prerequisites and complete run instructions. The repository does not specify a minimum Python version, a tested ESP32 board, or pinned Arduino library versions.

### Server

From the repository root, create a virtual environment and install the server requirements:

**Windows PowerShell:**

```powershell
cd server
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python main.py
```

**macOS/Linux:**

```bash
cd server
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python main.py
```

### Flutter

From the repository root:

```bash
cd smarthomeapp
flutter pub get
flutter test
flutter analyze
```

The current test suite contains a Flutter app-shell widget smoke test. It does not test the server or physical hardware. `analysis_options.yaml` enables the recommended `flutter_lints` rules.

### ESP32 firmware

Open `esp32_client/esp32_client.ino` in an Arduino-compatible IDE, select your ESP32 board and serial port, and install the libraries required by its includes: WebSocketsClient, ArduinoJson, ESP32Servo, DHT, and MFRC522. No board model, Arduino CLI command, or firmware test suite is specified by this repository. Check the README hardware cautions before connecting components; do not publish Wi-Fi credentials.

## Development workflow

1. Fork this repository on GitHub and clone the fork using the clone URL shown on the fork's **Code** menu.
2. Add the canonical repository as `upstream` and fetch its default branch:

   ```bash
   git remote add upstream https://github.com/trankhahao7/SmartHome.git
   git fetch upstream
   git switch main
   git pull --ff-only upstream main
   ```

3. Create a focused branch from `main`. Suggested prefixes are `feat/`, `fix/`, and `docs/`; they are conventions, not enforced repository policy.
4. Make one cohesive change. Add or update tests and documentation where appropriate.
5. Run the relevant checks from [Code, tests, and commits](#code-tests-and-commits).
6. Commit and push to your fork, then open a pull request against `main`.
7. Respond to review feedback and update the pull request. Maintainer review and merge decisions are handled per contribution; no approval count, response-time guarantee, or merge strategy is currently published.

## Code, tests, and commits

- Keep changes focused and follow the surrounding style. Dart analysis uses `flutter_lints`; run `flutter analyze` for Flutter changes.
- Run `flutter test` for Flutter changes. Add a regression test for a bug fix when the behavior can be covered by the current test setup.
- No server integration, hardware-in-the-loop, or CI test suite is currently provided. For changes in those areas, describe any manual checks and environment limitations in the pull request; do not claim an unrun test passed.
- Update the root README or the relevant `docs/` note when user-facing setup, configuration, behavior, or hardware instructions change. Keep examples free of real credentials and personal data.
- No commit-message format, DCO, CLA, changelog requirement, or AI-assisted contribution policy has been established. Use a concise, descriptive commit subject and ensure you have the right to submit the contribution under the project's license.

## Pull requests

Use the [pull request template](.github/PULL_REQUEST_TEMPLATE.md). Explain the problem and solution, link related issues, list the checks actually run, and call out breaking changes or hardware-specific behavior. Include screenshots for meaningful UI changes.

Keep each pull request small enough to review. Do not claim CI is required or passing; this repository currently has no GitHub Actions workflow. Maintainers may ask for changes, decline a contribution, or merge it using the approach appropriate to that pull request. No fixed review SLA or stale-pull-request policy is published.

## License

The project is distributed under the [MIT License](LICENSE). By submitting a contribution, you make it available under the applicable project license. Do not submit code or content that you do not have permission to contribute.
