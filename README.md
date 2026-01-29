# PracticeTab – Update Repository

This repository hosts signed update artifacts for the PracticeTab desktop application.

It is used exclusively by the app’s auto-update system and is not intended for direct use by end users.

___

## Purpose

PracticeTab is an offline-first desktop application.
Internet access is only used for:
	•	🔄 Checking for updates
	•	🔐 License activation (future feature)

This repository provides:
	•	Versioned release artifacts (macOS & Windows)
	•	Update metadata for the Tauri updater
	•	Cryptographic signatures to verify update integrity

___

## How Updates Work
	1.	The app starts
	2.	The updater checks the latest GitHub Release
	3.	The installed version is compared to the latest version
	4.	If a newer version exists:
	•	The update is downloaded
	•	Its signature is verified
	•	The app installs the update and restarts

No telemetry or background network traffic is involved.

___

## Repository Structure

Each release is published via GitHub Releases.

A release typically contains:

macOS
	•	.app.tar.gz or .dmg
	•	.sig (signature)

Windows
	•	.msi or .exe
	•	.sig (signature)

Metadata
	•	Version number
	•	Release notes
	•	Target platform info

All files are generated automatically via GitHub Actions.

__

Versioning

Versions follow semantic versioning:

``` 
MAJOR.MINOR.PATCH[-tag]
```
Examples:
	•	0.1.0
	•	0.1.1-dev-test
	•	0.2.0-beta

Only stable releases are offered to production users.
Pre-release tags are used for testers.

___

## Access & Security
	•	This repository is private
	•	Updates are accessed using a read-only GitHub token
	•	All update artifacts are cryptographically signed
	•	The app will refuse unsigned or tampered updates

___

## For Testers

If you are testing PracticeTab:
	•	You do not need to clone this repository
	•	Updates will be delivered automatically via the app
	•	If an update fails:
	•	Restart the app
	•	Check the release notes
	•	Report the issue to the developer

___

## For Developers
	•	Do not manually upload files
	•	Always use the automated build workflow
	•	Never remove existing releases
	•	Never re-upload artifacts with the same version number

Breaking these rules may invalidate updates for users.

___

## License

This repository and all contained artifacts are proprietary.

All rights reserved.
Redistribution or modification is not permitted without explicit permission.
