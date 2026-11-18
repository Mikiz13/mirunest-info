# MiruNest - Privacy Policy

**Last updated: November 18, 2026**

## 1. Introduction

MiruNest is a personal, non-commercial Android application developed for anime tracking and personal anime library management.

The application is intended for private use on the developer's own Android devices and is not publicly distributed.

MiruNest is an independent project and is not affiliated with, sponsored by, or endorsed by MyAnimeList.

## 2. Current Development Status

MiruNest is under active development.

**Version 0.4** supports MyAnimeList authentication, profile retrieval, secure session management, and access to the authenticated user's anime library.

Home and Library display real anime data retrieved through the official MyAnimeList API.

The Discover screen currently contains clearly identified demonstration content.

Version 0.4 includes an episode synchronization feature with a protected preview mode.

**Normal builds keep MyAnimeList write operations disabled.**

A separately configured, temporary test build may enable a strictly limited episode update after explicit user confirmation.

## 3. MyAnimeList Integration

MiruNest uses the official MyAnimeList API and OAuth authorization system.

The application supports:

- Authentication through the official MyAnimeList authorization process.
- Retrieval of the authenticated user's profile.
- Secure local authentication session management.
- Authentication token refresh.
- Retrieval of personal anime library entries.
- Display of anime titles, cover images, watch statuses, episode counts, personal ratings, and available alternative titles.
- Local searching, filtering, and sorting of retrieved anime.
- Manual library refreshing.
- Episode increment previews.
- Protected episode synchronization testing.
- Logout and local authentication credential removal.

MiruNest does not request or store the user's MyAnimeList password.

### Controlled Episode Synchronization

When explicitly enabled in a temporary test build, MiruNest may update the watched episode count of one specifically authorized anime.

This operation uses the official MyAnimeList API endpoint:

`PATCH /anime/{anime_id}/my_list_status`

Only the `num_watched_episodes` field is submitted for the controlled update.

The application requires explicit user confirmation before sending the update.

The controlled test includes restrictions on the selected anime, expected episode count, target episode count, and permitted write attempt.

A successful update changes the user's watch progress stored on MyAnimeList.

The application does not automatically modify personal ratings, comments, or other anime list fields during this test.

## 4. Data Access and Usage

MiruNest accesses information authorized through the user's MyAnimeList account, including:

- Account profile information.
- Authentication tokens and temporary OAuth authorization data.
- Personal anime library entries.
- Watched episode counts and anime statuses.
- Total episode counts.
- Personal anime ratings.
- Library update timestamps.
- Anime titles, alternative titles, and cover image URLs.

This information is used exclusively for the application's anime tracking and library functionality.

Controlled synchronization may transmit an updated episode count to MyAnimeList after explicit user confirmation.

MiruNest does not collect personal information for advertising or analytics.

## 5. Data Storage

MiruNest does not operate its own backend server for collecting or storing MyAnimeList account information.

Authentication tokens and temporary OAuth authorization data are encrypted locally using AES-GCM backed by Android Keystore.

Authentication storage is excluded from Android backup mechanisms.

Anime library records are retained in application memory and are not stored in a persistent local anime database.

Image-loading components may use memory or disk caching managed by their underlying libraries. Offline cover image availability is not guaranteed.

For controlled synchronization testing, the application maintains a private local record indicating whether the permitted write attempt has been used.

This record is intended to prevent repeated write attempts within the same application installation.

The record is not an absolute guarantee against repeated requests following application data deletion, reinstallation, or modification.

## 6. Data Sharing and External Services

MiruNest does not sell personal information and does not currently include advertising or third-party analytics services.

The application communicates with official MyAnimeList services for authentication, authorized information retrieval, and explicitly enabled episode synchronization.

Anime cover images and profile images are loaded from URLs provided by MyAnimeList and may be served through image-hosting infrastructure.

Authentication uses the device's browser, which manages its own sessions separately from MiruNest.

MyAnimeList processes information according to its own privacy policy:

[MyAnimeList Privacy Policy](https://myanimelist.net/about/privacy_policy)

## 7. Data Retention and Deletion

Authentication credentials remain stored locally until the user logs out, clears application data, or uninstalls MiruNest.

Logging out removes locally stored authentication credentials and clears the in-memory anime library.

Logging out does not necessarily revoke tokens on MyAnimeList's servers or terminate the separate browser session.

Controlled test records may remain stored locally after logout to prevent reuse of a write attempt.

Users can remove application data through Android system settings or by uninstalling MiruNest, subject to applicable Android storage and backup behavior.

Removing local MiruNest data does not delete information stored on MyAnimeList.

Changes successfully synchronized to MyAnimeList remain associated with the user's MyAnimeList account.

## 8. Security

MiruNest uses the official OAuth authorization process, including PKCE and authorization state validation.

Sensitive authentication information is protected using Android Keystore-backed encryption.

The application is designed to avoid exposing authentication tokens or account credentials in logs.

Controlled episode synchronization includes:

- Explicit user confirmation.
- Anime identity and title validation.
- Remote progress verification before writing.
- Episode count validation.
- Restrictions on permitted write operations.
- Duplicate-request prevention.
- A persistent local record of the write attempt.
- Error and timeout handling.
- Restrictions against automatic write retries.

These protections reduce the risk of unintended modifications but do not eliminate all possible risks.

In particular, remote verification and a subsequent update are not an atomic transaction. Concurrent modifications by other clients may still occur.

## 9. Changes to This Policy

This Privacy Policy may be updated as MiruNest evolves.

Changes will be published in this GitHub repository, particularly when additional synchronization features, persistent storage, or other data-processing capabilities are introduced.

## 10. Contact

For questions regarding MiruNest or this Privacy Policy, please visit:

[MiruNest GitHub Repository](https://github.com/Mikiz13/mirunest-info)

Please do not publish passwords, authentication tokens, authorization codes, or other sensitive information in public GitHub issues.
