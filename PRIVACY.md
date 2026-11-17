MiruNest - Privacy Policy

Last updated: November 17, 2026

1. Introduction

MiruNest is a personal, non-commercial Android application developed for anime tracking and personal anime library management.

The application is currently intended for private use on the developer's own Android devices and is not publicly distributed.

MiruNest is an independent project and is not affiliated with, sponsored by, or endorsed by MyAnimeList.

2. Current Development Status

MiruNest is under active development.

Version 0.2 supports MyAnimeList authentication, profile retrieval, encrypted local session storage, session persistence, token refresh, and logout.

The Home and Library features currently use demonstration data. Integration with the user's actual anime library, including watch progress synchronization, is planned for future versions.

3. MyAnimeList Integration

MiruNest uses the official MyAnimeList API and OAuth authorization system.

The current version can:

- Open the official MyAnimeList authorization page in the device's browser.
- Authenticate the user without accessing or storing their MyAnimeList password.
- Retrieve the authenticated user's profile, including username and profile image when available.
- Maintain and refresh the authenticated session.
- Remove locally stored authentication credentials when the user logs out.

Future versions may support anime library retrieval, anime search, watch progress synchronization, ratings, and anime status management.

MiruNest does not currently modify the user's MyAnimeList anime library.

4. Data Access and Usage

The current version accesses MyAnimeList profile information required to identify and display the authenticated account.

It also processes authentication tokens and temporary OAuth authorization data to maintain a working connection with MyAnimeList.

Future versions may access the following information through the official API:

- Personal anime library entries
- Anime watch statuses and watched episode counts
- Personal ratings and list update information
- Anime titles, descriptions, genres, images, and other available metadata

This information will be used exclusively to provide MiruNest's intended functionality.

5. Data Storage

MiruNest does not operate its own backend server for collecting or storing MyAnimeList account information.

Authentication tokens and temporary OAuth authorization data are stored locally on the Android device using AES-GCM encryption backed by Android Keystore.

Authentication storage is excluded from Android backup mechanisms.

The current version does not maintain a persistent local database of the user's MyAnimeList anime library.

Future versions may introduce limited, temporary on-device caching to improve performance and usability. This policy will be updated when such functionality is implemented.

6. Data Sharing and External Services

MiruNest does not sell personal information and does not currently include advertising or third-party analytics services.

The application communicates with MyAnimeList's official services for authentication and authorized profile retrieval.

Profile images may be loaded from image URLs supplied by MyAnimeList.

Authentication is completed through the device's browser, which manages its own browsing data and sessions independently of MiruNest.

MyAnimeList processes information according to its own privacy policy:

https://myanimelist.net/about/privacy_policy

7. Data Retention and Deletion

Authentication credentials remain stored locally until the user logs out, clears the application's data, or removes the application.

Logging out removes MiruNest's locally stored authentication credentials. It does not necessarily revoke tokens on MyAnimeList's servers or sign the user out of the browser.

Users can remove application data through Android system settings or by uninstalling the application, subject to the applicable Android storage and backup mechanisms.

Deleting MiruNest data does not delete or alter information stored on MyAnimeList.

8. Security

MiruNest uses the official OAuth authorization process, including PKCE and authorization state validation.

Sensitive authentication information is protected using Android Keystore-backed encryption.

The application is designed to avoid exposing authentication tokens or account credentials in application logs.

As a development project, MiruNest may receive further security improvements as its functionality evolves.

9. Changes to This Policy

This Privacy Policy may be updated as MiruNest evolves.

Changes will be published in this GitHub repository, including updates when additional MyAnimeList data access or local storage features are introduced.

10. Contact

For questions regarding MiruNest or this Privacy Policy, please visit:

https://github.com/Mikiz13/mirunest-info

Please do not publish passwords, authentication tokens, authorization codes, or other sensitive information in public GitHub issues.