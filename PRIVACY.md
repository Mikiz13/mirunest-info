# MiruNest - Privacy Policy

**Last updated: November 17, 2026**

## 1. Introduction

MiruNest is a personal, non-commercial Android application developed for anime tracking and personal anime library management.

The application is currently intended for private use on the developer's own Android devices and is not publicly distributed.

MiruNest is an independent project and is not affiliated with, sponsored by, or endorsed by MyAnimeList.

## 2. Current Development Status

MiruNest is under active development.

**Version 0.4** supports MyAnimeList authentication, profile retrieval, secure session management, and read-only access to the authenticated user's anime library.

The Home and Library screens display real anime data retrieved from MyAnimeList. The Discover screen currently contains clearly identified demonstration content.

Version 0.4 also includes a protected episode synchronization preview. This feature allows the user to preview a potential increase in watched episodes without submitting an update.

**Real anime library modifications remain disabled in the current protected version.**

## 3. MyAnimeList Integration

MiruNest uses the official MyAnimeList API and OAuth authorization system.

The current version can:

- Authenticate the user through the official MyAnimeList authorization process.
- Retrieve the authenticated user's profile and profile image when available.
- Maintain and refresh the authenticated session.
- Retrieve personal anime library entries through the official API.
- Display anime titles, cover images, watch statuses, watched episode counts, total episodes, personal ratings, and available alternative titles.
- Search, filter, and sort previously retrieved library entries locally.
- Refresh the anime library and display connection errors.
- Preview an increase of one watched episode without submitting any modification to MyAnimeList.
- Log out and clear locally stored authentication credentials and in-memory library data.

MiruNest does not request or store the user's MyAnimeList password.

**Version 0.4 runs with MyAnimeList write operations disabled.** Previewing an episode increment does not change the user's anime library.

Future versions may enable controlled watch progress synchronization, status management, anime search, and additional anime information.

## 4. Data Access and Usage

MiruNest accesses information authorized through the user's MyAnimeList account.

This includes:

- Account profile information.
- Authentication tokens and temporary authorization data.
- Personal anime library entries.
- Anime watch statuses and watched episode counts.
- Total episode counts and personal ratings.
- Library update timestamps.
- Anime titles, alternative titles, and cover image URLs.

This information is used exclusively to provide the application's anime tracking and library functionality.

Episode synchronization previews are calculated using available anime progress information.

MiruNest does not currently collect personal information for advertising or analytics.

## 5. Data Storage

MiruNest does not operate its own backend server for collecting or storing MyAnimeList account information.

Authentication tokens and temporary OAuth authorization data are encrypted locally using AES-GCM backed by Android Keystore.

Authentication storage is excluded from Android backup mechanisms.

In version 0.4, anime library records are retained in application memory during use and are not stored in a persistent local anime database.

Image-loading components may use temporary memory or disk caching managed by their underlying libraries. Offline availability of cover images is not guaranteed.

Future versions may introduce a local database or additional caching functionality. This policy will be updated when such features are implemented.

## 6. Data Sharing and External Services

MiruNest does not sell personal information and does not currently include advertising or third-party analytics services.

The application communicates with official MyAnimeList services for authentication and authorized data retrieval.

In the current protected version, episode synchronization previews do not transmit anime library modifications to MyAnimeList.

Anime cover images and profile images are loaded from URLs provided by MyAnimeList, which may be served through image-hosting infrastructure.

Authentication uses the device's browser, which manages its own sessions independently of MiruNest.

MyAnimeList processes information according to its own privacy policy:

[MyAnimeList Privacy Policy](https://myanimelist.net/about/privacy_policy)

## 7. Data Retention and Deletion

Authentication credentials are stored locally until the user logs out, clears application data, or uninstalls MiruNest.

Logging out removes locally stored authentication credentials and clears the in-memory anime library.

Logging out does not necessarily revoke tokens on MyAnimeList's servers or end the separate browser session.

The user can remove application data through Android system settings or by uninstalling the application, subject to applicable Android storage and backup behavior.

Removing local MiruNest data does not delete or alter information stored on MyAnimeList.

## 8. Security

MiruNest uses the official OAuth authorization process, including PKCE and authorization state validation.

Sensitive authentication information is protected through Android Keystore-backed encryption.

The application is designed to avoid exposing authentication tokens or account credentials in logs.

Version 0.4 includes safeguards for future episode synchronization, including validation of episode limits, remote progress verification, duplicate-request prevention, and error handling.

**The current protected build keeps real MyAnimeList write operations disabled.**

These safeguards do not guarantee protection against every possible error or concurrent modification. Additional verification will be performed before enabling real synchronization.

## 9. Changes to This Policy

This Privacy Policy may be updated as MiruNest evolves.

Changes will be published in this GitHub repository, particularly when new data access, synchronization, or persistent storage features are introduced.

**This policy will be updated to describe real write operations before episode synchronization is enabled for actual use.**

## 10. Contact

For questions regarding MiruNest or this Privacy Policy, please visit:

[MiruNest GitHub Repository](https://github.com/Mikiz13/mirunest-info)

Please do not publish passwords, authentication tokens, authorization codes, or other sensitive information in public GitHub issues.
