# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2022-01-10

### Added

- Initial Release

### Changed

- Initial Release

### Removed

- Initial Release

## [1.1.0] - 2022-01-11

### Changed

- Default Ruby changed to 3.0.3.
- Default Postgres changed to 12.9.

## [1.2.0] - 2022-01-12

### Added

- Install Firefox option to test-rails.
- Install Java option to test-rails.

### Changed

- Fixed example.

### Removed

- Removed parallelism from test-rails and test-gem since breaking code coverage.

## [2.1.0] - 2022-02-18

### Changed

- Added caching to Rubocop runs

## [3.0.0] - 2022-02-22

### Changed

- Bumped dependency orbs to latest

## [3.0.1] - 2022-02-25

### Added

- Added lint-gem job appropriate for using with gems

## [3.1.1] - 2022-05-23

### Changed

- Stop using sudo to install openapi-enforcer-cli package

## [3.2.0] - 2023-01-30

### Added

- Adds extra_build_args param to docker/build.

## [4.0.0] - 2023-05-12

### Changed

- Default Ruby changed to 3.2.2.

## [4.1.0] - 2023-08-18

### Changed

- Updated to latest orbs.
- Enabled rerun-fail for ruby tests.

## [4.3.0] - 2025-01-27

### Changed

- Updated to latest orbs.
- Updated to Ruby 3.4.1.

## [4.4.0] - 2025-01-30

### Changed

- Add support for CodeCov (eventual replacement for CodeClimate, we hope)

## [4.5.0] - 2025-03-11

### Changed

- Remove support for CodeClimate

## [4.7.0] = 2026-03-20

### Changed

- Added optional job-level parallelism support back to `test-rails` and `test-gem`.
- Adds stylelint.
- Adds herblint.

## [4.8.0] = 2026-05-06

### Changed

- Updated ruby orb to 2.6.0.

## [4.9.0] = 2026-06-03

### Changed

- Updated docker orb to 4.0.0.
- Build docker images from amd64 and arm64 by default.

## [4.10.0] = 2026-06-08

### Changed

- Updated circleci orb to 6.0.0
