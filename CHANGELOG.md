# CHANGELOG

## [Untagged]

No date

- If there are any changes since the last tag, click [here][untagged] to see the changes.

## [0.15.3]

22.07.2020

- Fixed another small piece of failed logic around the check for whether there is already an installer which was finding other apps with `macOS` in the name. Now, only apps with `Install macOS*.app` will be found.

## [0.15.2]

14.07.2020

- Fixed some failed logic around the check for whether there is already an installer in the `/Applications` folder which was erroneously also looking in other locations.

## [0.15.1]

23.06.2020

- Parameters can now be supplied as `--argument value` as an alternative to `--argument=value` to provide more consistency with the included tools (`installinstallmacos.py` and `softwareupdate`).

## [0.15.0]

09.06.2020

- Adds `--allowremoval` option to the `startosinstall` command by default. This is an undocumented flag which is required under certain circumstances where there are backup files on the system disk.

## [0.14.0]

06.05.2020

- Adds `--replace_invalid` option for the option to overwrite a cached installer if it is not valid for use with `--erase` or `--reinstall`.
- Adds `--update` option for the option to overwrite a cached installer if a newer installer is available.

## [0.13.0]

04.05.2020

- Adds `--preservecontainer` option for workflows that need to retain a container when performing `eraseinstall`.
- Adds additional flags to `caffeinate` to attempt to more robustly prevent device sleeping.
- Fix for missing heading in the full screen display of the `--reinstall` option.
- Added a test script `tests/test-erase-install.sh` for testing out functionality.

## [0.12.1]

14.04.2020

- Use `--forcequitapps` when _using_ the macOS Catalina installer, rather than just when _running_ on a macOS Catalina client (issue #25).

## [0.12.0]

13.02.2020

- Removed downloaded OS validity check for modes where the installer is not required for reinstall or eraseinstall, to prevent unnecessary exit failures.
- Fixed a problem preveting `--move` from working when overwriting a valid installer.
- Other small bugfixes.

## [0.11.1]

03.02.2020

- Restricted the add forcequitapps install_args option to macOS 10.15 or greater, as this is not functional with older versions (#35). Thanks to '@ahousseini' for the contribution.

## [0.11.0]

22.01.2020

- Added the `--sameos` option, so you can have a single command which will always try to reinstall whatever macOS (major) version is currently installed on the host.

## [0.10.1]

11.12.2019

- Removed check that a user is logged in before proceeding with startosinstall - apparently not necessary after all, and caused at least one user's workflow to break (#33).

## [0.10.0]

27.11.2019

- Add a check that there is enough disk space before proceeding
- Added --forcequitapps argument for 10.15 and above
- Check that a user is logged in before proceeding with startosinstall
- Improved find commands when checking that there is a mounted installer
- Improved German descriptions for reinstallation
- Improved checks for successful downloads from the --fetch_full_installer option

Thanks to '@ahousseini' for various contributions to this release

## [0.9.1]

15.11.2019

- Move a comment that states that --fetch-full-installer is available to the correct place (#31)

## [0.9.0]

07.10.2019

- Added support for `softwareupdate --fetch-full-installer` and `seedutil` for clients running macOS 10.15 or greater.

## [0.8.0]

27.09.2019

- Fixed caffeinate (forgot to make it a background process)
- Added 'Confirm' option for erasing. Thanks to '@ryan-alectrona' for the contribution.

## [0.7.1]

26.09.2019

- Added caffeinate to the script to prevent the computer going to sleep during long download phases etc.

## [0.7.0]

12.07.2019

- Added `--beta` option.
- Changed behaviour of `--os`, `--version` and auto (i.e. no flag) options to get the latest rather than earliest valid build.
- Removed `install-macos.sh` script. Use `erase-install.sh` with `--reinstall` option instead.

## [0.6.0]

19.06.2019

- Added `--reinstall` option, which obsoletes the `install-macos.sh` script.

## [0.5.0]

16.04.2019

- Bug fix for empty extra packages folder.  
  Thanks to '@Avartharian' for contributions
- Added `--catalogurl` and `--seedprogram` options

## [0.4.0]

02.04.2019

- Added localisation of Jamf Helper messages.  
  Thanks to '@ahousseini' for contributions
- Added `--os`, `--path`, `--extras`, `--list` options.  
  Thanks to '@mark lamont' for contributions

## [0.3.2]

13.12.2018

- Bug fix for `--build` option, and for exiting gracefully when nothing is downloaded.

## [0.3.1]

21.09.2018

- Added ability to specify a macOS version.
- Fixed the `--overwrite` flag.
- Added ability to specify a build in the parameters, and we now clear out the cached content.

## [0.3.0]

03.09.2018

- Additional and amended options for selecting non-standard builds.

## [0.2.0]

09.07.2018

- Automatically selects a non-beta installer.

## 0.1.0

29.03.2018

- Initial version. Expects a manual choice of installer from `installinstallmacos.py`.

[untagged]: https://github.com/grahampugh/erase-install/compare/v0.15.2...HEAD
[0.15.3]: https://github.com/grahampugh/erase-install/compare/v0.15.2...v0.15.3
[0.15.2]: https://github.com/grahampugh/erase-install/compare/v0.15.1...v0.15.2
[0.15.1]: https://github.com/grahampugh/erase-install/compare/v0.15.0...v0.15.1
[0.15.0]: https://github.com/grahampugh/erase-install/compare/v0.14.0...v0.15.0
[0.14.0]: https://github.com/grahampugh/erase-install/compare/v0.13.0...v0.14.0
[0.13.0]: https://github.com/grahampugh/erase-install/compare/v0.12.1...v0.13.0
[0.12.1]: https://github.com/grahampugh/erase-install/compare/v0.12.0...v0.12.1
[0.12.0]: https://github.com/grahampugh/erase-install/compare/v0.11.1...v0.12.0
[0.11.1]: https://github.com/grahampugh/erase-install/compare/v0.11.0...v0.11.1
[0.11.0]: https://github.com/grahampugh/erase-install/compare/v0.10.1...v0.11.0
[0.10.1]: https://github.com/grahampugh/erase-install/compare/v0.10.0...v0.10.1
[0.10.0]: https://github.com/grahampugh/erase-install/compare/v0.9.1...v0.10.0
[0.9.1]: https://github.com/grahampugh/erase-install/compare/v0.9.0...v0.9.1
[0.9.0]: https://github.com/grahampugh/erase-install/compare/v0.8.0...v0.9.0
[0.8.0]: https://github.com/grahampugh/erase-install/compare/v0.7.1...v0.8.0
[0.7.1]: https://github.com/grahampugh/erase-install/compare/v0.7.0...v0.7.1
[0.7.0]: https://github.com/grahampugh/erase-install/compare/v0.6.0...v0.7.0
[0.6.0]: https://github.com/grahampugh/erase-install/compare/v0.5.0...v0.6.0
[0.5.0]: https://github.com/grahampugh/erase-install/compare/v0.4.0...v0.5.0
[0.4.0]: https://github.com/grahampugh/erase-install/compare/v0.3.2...v0.4.0
[0.3.2]: https://github.com/grahampugh/erase-install/compare/v0.3.1...v0.3.2
[0.3.1]: https://github.com/grahampugh/erase-install/compare/v0.3.0...v0.3.1
[0.3.0]: https://github.com/grahampugh/erase-install/compare/v0.2.0...v0.3.0
[0.2.0]: https://github.com/grahampugh/erase-install/compare/v0.1.0...v0.2.0
