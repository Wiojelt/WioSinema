# Implementation Plan: WioSinema Unified Catalog & Provider Aggregator

**Feature Branch**: `001-featurename-wiosinema-unified`
**Specification**: `specs/001-featurename-wiosinema-unified/spec.md`
**Status**: Draft

## 1. Architecture & Design

### Component Diagram

```
+-------------------------------------------------------------+
|                      Cloudstream App                        |
+------------------------------+------------------------------+
                               |
                               v
               +-------------------------------+
               |       WioSinemaProvider       |
               +---------------+---------------+
                               |
        +----------------------+----------------------+
        |                                             |
        v                                             v
+-----------------------+                 +-----------------------+
|   TmdbCatalogEngine   |                 | ConcurrentStreamEngine|
|  (Categories/Posters/ |                 | (Parallel Scraping &  |
|   IMDb & TR details)  |                 |  TV Box Concurrency)  |
+-----------------------+                 +-----------+-----------+
                                                      |
                                    +-----------------+-----------------+
                                    |                 |                 |
                                    v                 v                 v
                              [HDFilmCehennemi]   [Dizilla]        [FilmModu / ...]
```

---

## 2. Directory & Module Structure

WioSinema will be integrated both as a subproject inside `TurkSinema-Source` (sharing build tools & providers) and as an independent repository `WioSinema`:

```
WioSinema/
├── src/main/kotlin/wiosinema/
│   ├── WioSinemaPlugin.kt           # Plugin entry, settings UI, TV Box mode toggle
│   ├── WioSinemaProvider.kt         # MainAPI (loadMainPage, search, load, loadLinks)
│   ├── catalog/
│   │   ├── TmdbCatalog.kt           # TMDB API v3 endpoints, categories, tr-TR mapper
│   │   └── CatalogModels.kt         # DTOs for TMDB responses
│   ├── aggregator/
│   │   ├── StreamAggregator.kt      # Parallel query orchestrator with Semaphore
│   │   ├── TitleMatcher.kt          # Turkish title & year normalization
│   │   └── ProviderAdapter.kt       # Unified interface wrapping TurkSinema providers
│   ├── providers/                   # Core provider scrapers adapted for aggregation
│   │   ├── HDFilmCehennemiAdapter.kt
│   │   ├── DizillaAdapter.kt
│   │   ├── FilmModuAdapter.kt
│   │   ├── FilmMakinesiAdapter.kt
│   │   └── InatBoxAdapter.kt
│   └── common/
│       ├── DomainResolver.kt        # Dynamic domain resolver
│       └── SupportNotice.kt         # Standard Wio support notice
└── src/test/kotlin/wiosinema/
    ├── TitleMatcherTest.kt
    └── TmdbCatalogTest.kt
```

---

## 3. Implementation Phases

1. **Phase 1: TMDB Catalog & UI Integration**
   - Implement `TmdbCatalog.kt` to fetch Trending Movies, In Theatres, Popular TV Shows, Top Rated IMDb, Genres in Turkish (`tr-TR`).
   - Wire into `WioSinemaProvider.getMainPage` and `search`.

2. **Phase 2: Stream Aggregator & Title Matcher**
   - Implement `TitleMatcher.kt` with comprehensive Turkish diacritic normalization and regex matching.
   - Implement `StreamAggregator.kt` with coroutines, `Semaphore(permits = 3)` for TV Box mode (or 8 for normal mode), and 6-second per-provider timeout.

3. **Phase 3: Core Provider Adapters**
   - Connect top Turkish streaming sources: HDFilmCehennemi, Dizilla, FilmModu, FilmMakinesi, InatBox, FullHDFilm.
   - Extract stream URLs, subtitles, qualities, and tag them with provider badges.

4. **Phase 4: TV Box Mode & Settings UI**
   - Add translucent TV-box remote-friendly settings UI.
   - Add provider selection toggles and TV Box mode switch.

5. **Phase 5: Build, Test & Deploy**
   - Gradle configuration and `.cs3` packaging.
   - Device testing on Android TV / mobile (`127.0.0.1:16384`).
