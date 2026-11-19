# MiruNest - Privacy Policy

**Last updated: November 18, 2026**

## 1. Introduction

MiruNest is a personal, non-commercial Android application developed for anime tracking and personal anime library management.

The application is intended for private use on the developer's own Android devices and is not publicly distributed.

MiruNest is an independent project and is not affiliated with, sponsored by, or endorsed by MyAnimeList.

## 2. Current Development Status

MiruNest is under active development.

**Version 0.5** supports authentication, profile retrieval, personal anime library access, protected episode synchronization, and real anime catalog discovery.

Home and Library display real anime data retrieved through the official MyAnimeList API.

The Discover screen uses the official MyAnimeList API to search the anime catalog and retrieve detailed anime information, including titles, alternative titles, cover images, synopses, episode counts, publication information, scores, genres, and studios, where available.

Anime catalog discovery is read-only. Searching for or viewing an anime does not add it to the user's library or modify MyAnimeList account data.

Daily episode synchronization remains available in explicitly enabled personal builds, with user confirmation required before each update. Default project builds retain write operations disabled.

## 3. MyAnimeList Integration

MiruNest uses the official MyAnimeList API and OAuth authorization system.

Current features include:

- Authentication through the official MyAnimeList authorization process.
- Retrieval of account profile information.
- Secure local authentication session management.
- Authentication token refresh.
- Retrieval of personal anime library entries.
- Display of anime titles, cover images, watch statuses, episode counts, personal ratings, and alternative titles.
- Local searching, filtering, and sorting.
- Manual library refreshing.
- Episode increment previews.
- Protected episode synchronization testing.
- Logout and local authentication credential removal.
- Search of the official MyAnimeList anime catalog.
- Retrieval and display of detailed anime information through official MyAnimeList read-only API endpoints.

MiruNest does not request or store the user's MyAnimeList password.

### Episode Synchronization

MiruNest includes functionality designed to update watched episode counts using the official MyAnimeList API.

When synchronization is explicitly enabled, an authorized update may be sent through:

`PATCH /anime/{anime_id}/my_list_status`

The update submits only the `num_watched_episodes` field.

Each update requires explicit user confirmation.

The application checks the remote anime progress before attempting an update.

Synchronization does not automatically change personal ratings, comments, or anime list statuses.

### Controlled Testing

MiruNest previously completed a controlled synchronization test involving one specifically authorized anime.

The controlled test used a restricted configuration and a persistent local attempt record to prevent repeated submissions.

The controlled testing mechanism remains separate from normal daily synchronization.

### Daily Episode Synchronization

Daily episode synchronization is available in explicitly enabled personal builds and allows users to update eligible anime without configuring an individual anime ID.

Each update requires explicit user confirmation and validation of the current remote progress.

The application is designed to prevent duplicate submissions and automatic retries after uncertain results.

Daily synchronization is disabled by default in standard project builds and enabled only through a separate local configuration.

## 4. Data Access and Usage

MiruNest accesses information authorized through the user's MyAnimeList account, including:

- Account profile information.
- Authentication tokens and temporary OAuth authorization data.
- Personal anime library entries.
- Anime watch statuses and watched episode counts.
- Total episode counts.
- Personal ratings.
- Library update timestamps.
- Anime titles, alternative titles, and cover image URLs.

This information is used exclusively to provide the application's anime tracking and library functionality.

When synchronization is enabled and the user confirms an update, MiruNest transmits the authorized watched episode count to MyAnimeList.

MiruNest does not collect personal information for advertising or analytics.

## 5. Data Storage

MiruNest does not operate its own backend server for collecting or storing MyAnimeList account information.

Authentication tokens and temporary OAuth authorization data are encrypted locally using AES-GCM backed by Android Keystore.

Authentication storage is excluded from Android backup mechanisms.

Anime library information is retained in application memory and is not currently maintained in a persistent local anime database.

Image-loading components may use temporary memory or disk caching managed by their underlying libraries. Offline availability of cover images is not guaranteed.

MiruNest uses private local synchronization records to track controlled write attempts and potentially unresolved daily synchronization operations.

These records help prevent duplicate updates and support recovery after uncertain results.

Local safeguards cannot guarantee protection against all concurrent modifications or data loss caused by clearing application storage or reinstalling the application.

## 6. Data Sharing and External Services

MiruNest does not sell personal information and does not currently include advertising or third-party analytics services.

The application communicates with official MyAnimeList services for authentication, authorized information retrieval, and explicitly enabled episode synchronization.

Anime cover images and profile images are loaded from URLs provided by MyAnimeList, which may be served through image-hosting infrastructure.

Authentication uses the device's browser, which manages its own sessions independently of MiruNest.

MyAnimeList processes information according to its own privacy policy:

[MyAnimeList Privacy Policy](https://myanimelist.net/about/privacy_policy)

## 7. Data Retention and Deletion

Authentication credentials remain stored locally until the user logs out, clears application data, or uninstalls MiruNest.

Logging out removes locally stored authentication credentials and clears the in-memory anime library.

Logging out does not necessarily revoke tokens on MyAnimeList's servers or terminate the separate browser session.

Some local synchronization safety records may remain after logout to prevent unintended repeated write attempts.

Users can remove application data through Android system settings or by uninstalling MiruNest, subject to applicable Android storage and backup behavior.

Removing local MiruNest data does not delete information stored on MyAnimeList.

Successfully synchronized changes remain associated with the user's MyAnimeList account.

## 8. Security

MiruNest uses the official OAuth authorization process, including PKCE and authorization state validation.

Sensitive authentication information is protected using Android Keystore-backed encryption.

The application is designed to avoid exposing authentication tokens or account credentials in logs.

Episode synchronization safeguards include:

- Explicit user confirmation.
- Remote progress verification before writing.
- Validation of eligible anime and episode counts.
- Prevention of simultaneous write operations.
- Protection against duplicate submissions.
- Private records for unresolved synchronization operations.
- Read-only verification following uncertain results.
- Restrictions against automatic write retries.
- Protection against stale responses following logout or account changes.

These safeguards reduce the risk of unintended modifications but cannot eliminate all possible errors.

In particular, a remote read followed by an update is not an atomic transaction. Concurrent modifications by other clients remain possible.

## 9. Changes to This Policy

This Privacy Policy may be updated as MiruNest evolves.

Changes will be published in this GitHub repository, especially when new synchronization, local storage, or data-processing capabilities are introduced.

## 10. Contact

For questions regarding MiruNest or this Privacy Policy, please visit:

[MiruNest GitHub Repository](https://github.com/Mikiz13/mirunest-info)

Please do not publish passwords, authentication tokens, authorization codes, or other sensitive information in public GitHub issues.
