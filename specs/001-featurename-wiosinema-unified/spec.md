# Feature Specification: WioSinema Unified Catalog and Multi-Provider Stream Aggregator

**Feature Branch**: `001-featurename-wiosinema-unified`
**Created**: 2026-09-12
**Status**: Draft
**Input**: WioSinema unified movie/series catalog with TMDB/IMDb metadata and multi-provider stream aggregator

## 1. Overview & Goal

WioSinema transforms the fragmented 50+ TurkSinema providers into a single, polished, high-performance Cloudstream plugin. Users browse a unified catalog (categories, posters, IMDb scores, descriptions, trailers) powered by TMDB/IMDb metadata. When playback is requested, WioSinema queries Turkish streaming providers in parallel to discover and aggregate all playable links with quality and source labels.

---

## 2. User Scenarios & Prioritization

### User Story 1 - Unified Catalog Browsing (Priority: P1)
As a viewer, I want to browse unified home page categories (Popüler Filmler, Vizyondakiler, En İyi IMDb Puanlılar, Popüler Diziler, Platformlara Göre İçerikler) with posters and IMDb ratings, without navigating individual site scrapers.

- **Independent Test**: Open WioSinema home page in Cloudstream, verify categories load with Turkish titles, poster images, year, and rating badges.
- **Acceptance Criteria**:
  1. Given the home page loads, Then categories (Trend Filmler, IMDb Top, Popüler Diziler, Türler) are populated.
  2. Given any movie or series card is selected, Then details screen displays backdrop, poster, Turkish summary, release year, duration, genres, and IMDb score.

---

### User Story 2 - Multi-Provider Concurrent Stream Aggregation (Priority: P1)
As a viewer, when I select a movie or series episode, I want WioSinema to automatically search and fetch stream links from all available Turkish providers (HDFilmCehennemi, Dizilla, DiziBox, FilmModu, InatBox, FullHDFilm, etc.) and present them in one unified link list.

- **Independent Test**: Tap Play on a well-known title (e.g. "Interstellar" or "Breaking Bad S01E01"), verify links are fetched from multiple providers concurrently with provider name and quality tags.
- **Acceptance Criteria**:
  1. Given a movie is opened, When playback starts, Then link fetchers query enabled Turkish cinema providers in parallel.
  2. Given streams are found, Then each link displays the provider source (e.g. `[HDFilmCehennemi] 1080p`, `[Dizilla] Dublaj 1080p`).
  3. Given one or more providers fail or time out, Then successful links from other providers are unaffected and displayed immediately.

---

### User Story 3 - Search Across Unified Catalog & Providers (Priority: P2)
As a viewer, I want to search for any title in Turkish or English, see instant matching results from TMDB, and click to load streams from all providers.

- **Independent Test**: Search for "Yüzüklerin Efendisi" or "The Lord of the Rings", select the item, and verify links resolve from Turkish providers.
- **Acceptance Criteria**:
  1. Given a search query, Then auto-completed search results display posters and years.
  2. Given a selected search result, Then the content detail view opens with full season/episode list (for series) or stream resolvers (for movies).

---

### User Story 4 - TV Box Mode & Provider Configuration (Priority: P2)
As a TV Box user with low RAM, I want to limit the number of concurrent provider searches and customize which providers are enabled so the app does not freeze or crash.

- **Independent Test**: Toggle "TV Box Modu" in settings, verify maximum concurrent scraper coroutines are restricted (e.g. Semaphore = 4) and first-response links load quickly.
- **Acceptance Criteria**:
  1. Given TV Box mode is enabled, When links are fetched, Then concurrency is capped and memory usage stays low.
  2. Given provider settings, Then user can enable/disable specific providers.

---

## 3. Technical Requirements & Architecture

1. **Metadata Source**:
   - TMDB API (v3) / Simkl for rich catalog metadata (multilingual: Turkish `tr-TR` primary, English fallback).
   - Clean data mapping to Cloudstream's `MovieSearchResponse`, `TvSeriesSearchResponse`, `Episode`.

2. **Stream Resolver Engine**:
   - Match TMDB movie title / original title + year against Turkish provider search endpoints.
   - For series, match series title, season index, and episode index across providers.
   - Provider registry with modular extractor integration:
     - `HDFilmCehennemi`, `FilmMakinesi`, `Dizilla`, `DiziBox`, `FilmModu`, `InatBox`, `FullHDFilm`, `SetFilmIzle`, `JetFilmizle`, `KultFilmler`, `DiziPal`, `WebteIzle`, `SezonlukDizi`, etc.
   - Kotlin Coroutines with `SupervisorJob` + timeout (per provider: 6s timeout).
   - Deduplication of stream URLs.

3. **Domain & Network Layer**:
   - Shared domain resolver for dynamic Turkish domains (`domains.json` support).
   - Cloudflare clearance / User-Agent rotation helper.

---

## 4. Verification & Success Criteria

1. **Unit & Integration Tests**:
   - TMDB parser and Turkish title normalization tests.
   - Provider title matching algorithm tests (Turkish character mapping, e.g. `ı -> i`, `ç -> c`, year matching).
   - Link aggregation concurrency & timeout resilience tests.
2. **Build Verification**:
   - Gradle builds `.cs3` artifact without errors.
   - Tested on Android device/emulator (`127.0.0.1:16384`).
