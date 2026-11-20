# MiruNest - Privacy Policy

**Last updated: November 20, 2026**

## 1. Introduction

MiruNest is a personal, non-commercial Android application developed for anime tracking and personal anime library management.

The application is intended for private use on the developer's own Android devices and is not publicly distributed.

MiruNest is an independent project and is not affiliated with, sponsored by, or endorsed by MyAnimeList.

## 2. Current Development Status

MiruNest is under active development.

**Version 0.6** includes:

- Authentication and profile retrieval through the official MyAnimeList API.
- Real personal anime library synchronization.
- Daily watched-episode updates in explicitly enabled personal builds.
- Real anime catalog search and detailed anime information.
- Protected library management for adding anime and modifying viewing statuses, personal scores, and watched episode counts.

Home and Library display real data retrieved from MyAnimeList.

Discover provides real anime catalog search and read-only details.

**New library management write operations introduced in version 0.6 are currently disabled.** Users can prepare and preview changes, but these operations cannot submit updates in the protected version.

Daily episode synchronization remains independently available in explicitly enabled personal builds. Standard project builds retain write operations disabled by default.

## 3. MyAnimeList Integration

MiruNest uses the official MyAnimeList API and OAuth authorization system.

Features include:

- Official MyAnimeList account authorization.
- Account profile retrieval.
- Secure local authentication session management.
- Authentication token refresh.
- Retrieval of personal anime library entries.
- Display of titles, alternative titles, cover images, viewing statuses, watched episodes, and personal ratings.
- Local library searching, filtering, and sorting.
- Manual library refreshing.
- Official anime catalog search.
- Detailed anime information retrieval.
- Daily watched-episode synchronization where enabled.
- Protected previews for library management operations.
- Logout and local authentication credential removal.

MiruNest does not request or store the user's MyAnimeList password.

### Anime Catalog Discovery

MiruNest searches the official MyAnimeList anime catalog through supported read-only API endpoints.

Available information may include titles, alternative titles, cover images, synopsis, episode counts, publication information, genres, studios, and community scores.

Search results depend on the information and search capabilities provided by MyAnimeList.

Catalog searches and viewing anime details do not modify MyAnimeList account data.

### Daily Episode Synchronization

Daily episode synchronization is available in explicitly enabled personal builds.

It allows users to increment the watched episode count of eligible anime through the official MyAnimeList API.

Each update requires explicit user confirmation and verification of the current remote progress.

The application submits only the authorized watched episode count.

Daily synchronization is designed to prevent duplicate submissions and automatic retries following uncertain results.

This feature is disabled in default project builds and enabled only through a separate local configuration.

### Library Management

Version 0.6 introduces protected library management features designed to support:

- Adding an anime to the personal library.
- Changing an anime's viewing status.
- Assigning or clearing a personal score.
- Manually adjusting watched episode counts.

Supported viewing statuses include Watching, Completed, On Hold, Dropped, and Plan to Watch.

These operations use officially supported MyAnimeList API functionality.

When explicitly enabled in a future authorized build, each operation will require confirmation and validation before submitting a change.

The application is designed to submit only the field associated with the confirmed action, such as `status`, `score`, or `num_watched_episodes`.

Library management operations do not automatically modify unrelated fields.

**In the current protected version 0.6 build, these new write operations remain disabled.**

The existing daily episode synchronization feature uses separate authorization controls.

### Controlled Synchronization Testing

MiruNest previously performed a controlled episode synchronization test with one specifically authorized anime.

This test used a restricted configuration and a persistent local attempt record.

The controlled test mechanism remains separate from normal daily synchronization and library management.

## 4. Data Access and Usage

MiruNest accesses information authorized through the user's MyAnimeList account, including:

- Account profile information.
- Authentication tokens and temporary OAuth authorization data.
- Personal anime library entries.
- Viewing statuses.
- Watched episode counts.
- Total episode counts.
- Personal ratings.
- Library update timestamps.
- Anime titles, alternative titles, and cover image URLs.
- Public catalog information retrieved through official API endpoints.

This information is used to provide the application's anime tracking and library management functionality.

When a write feature is explicitly enabled and the user confirms an operation, MiruNest may transmit the authorized update to MyAnimeList.

MiruNest does not collect personal information for advertising or analytics.

## 5. Data Storage

MiruNest does not operate its own backend server for collecting or storing MyAnimeList account information.

Authentication tokens and temporary OAuth authorization data are encrypted locally using AES-GCM backed by Android Keystore.

Authentication storage is excluded from Android backup mechanisms.

Anime library information is retained in application memory and is not currently maintained in a persistent local anime database.

Image-loading components may use temporary memory or disk caching managed by their underlying libraries.

Offline availability of cover images is not guaranteed.

MiruNest maintains private local synchronization safety records for:

- Controlled synchronization testing.
- Potentially unresolved daily episode updates.
- Potentially unresolved library management operations.

These records help prevent duplicate submissions and distinguish different types of write operations.

Records associated with uncertain operations may contain technical identifiers and expected update values needed for verification.

Some safety records may persist after logout or application restart.

Local records and safeguards cannot completely prevent concurrent modifications, remote processing delays, or data loss caused by clearing application storage or reinstalling the application.

## 6. Data Sharing and External Services

MiruNest does not sell personal information and does not currently include advertising or third-party analytics services.

The application communicates with official MyAnimeList services for:

- Account authorization.
- Profile and library retrieval.
- Anime catalog discovery.
- Authorized episode synchronization.
- Other explicitly enabled and confirmed library management operations.

Anime cover images and profile images are loaded from URLs provided by MyAnimeList and may be served through image-hosting infrastructure.

Authentication uses the device's browser, which manages its own sessions separately from MiruNest.

MyAnimeList processes information according to its own privacy policy:

[MyAnimeList Privacy Policy](https://myanimelist.net/about/privacy_policy)

## 7. Data Retention and Deletion

Authentication credentials remain stored locally until the user logs out, clears application data, or uninstalls MiruNest.

Logging out removes locally stored authentication credentials and clears the in-memory anime library.

Logging out does not necessarily revoke tokens on MyAnimeList's servers or terminate the browser session.

Some synchronization safety records may remain after logout to prevent unintended repeated write attempts.

Users can clear application data through Android settings or uninstall MiruNest, subject to applicable Android storage and backup behavior.

Removing local application data does not delete information stored on MyAnimeList.

Successfully synchronized changes remain associated with the user's MyAnimeList account.

## 8. Security

MiruNest uses the official OAuth authorization process, including PKCE and authorization state validation.

Sensitive authentication information is protected using Android Keystore-backed encryption.

The application is designed to avoid exposing authentication tokens and account credentials in logs.

Synchronization safeguards include:

- Explicit user confirmation before write operations.
- Verification of remote information before updating.
- Validation of anime IDs and permitted field values.
- Separate authorization controls for different write features.
- Prevention of concurrent write operations.
- Protection against duplicate submissions.
- Persistent local records for unresolved operations.
- Read-only verification after uncertain results.
- Restrictions against automatic write retries.
- Session isolation following logout or account changes.
- Validation of supported HTTP methods, destinations, and request fields.

These safeguards reduce the risk of unintended modifications but cannot eliminate all possible errors.

In particular, a remote GET followed by a PATCH is not an atomic transaction. Concurrent changes by other clients remain possible.

A request already received by MyAnimeList may also complete after a client-side timeout.

## 9. Changes to This Policy

This Privacy Policy may be updated as MiruNest evolves.

Changes will be published in this GitHub repository, particularly when new synchronization, storage, or data-processing capabilities are enabled.

## 10. Contact

For questions regarding MiruNest or this Privacy Policy, please visit:

[MiruNest GitHub Repository](https://github.com/Mikiz13/mirunest-info)

Please do not publish passwords, authentication tokens, authorization codes, or other sensitive information in public GitHub issues.
