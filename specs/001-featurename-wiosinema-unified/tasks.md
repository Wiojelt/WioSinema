# Task List: WioSinema Implementation

**Feature Branch**: `001-featurename-wiosinema-unified`
**Plan**: `specs/001-featurename-wiosinema-unified/plan.md`
**Status**: Ready

## Tasks

- [ ] **Task 1: Project & Gradle Setup** (Est: 3m)
  - Configure `WioSinema` submodule inside `TurkSinema-Source/settings.gradle.kts` and root `build.gradle.kts`.
  - Create directory structure: `src/main/kotlin/wiosinema/` and `src/test/kotlin/wiosinema/`.

- [ ] **Task 2: TMDB Catalog Engine & Data Models** (Est: 5m)
  - Implement `CatalogModels.kt` (TMDB DTOs, SearchResults, Movie/Tv Details, Genres).
  - Implement `TmdbCatalog.kt` supporting Turkish language (`tr-TR`), trending movies/series, top rated IMDb, genres.
  - Implement `TmdbCatalogTest.kt` unit test.

- [ ] **Task 3: TitleMatcher & Provider Scraper Adapters** (Est: 6m)
  - Implement `TitleMatcher.kt` (Turkish diacritic normalization, year matching, punctuation stripping).
  - Add `TitleMatcherTest.kt` verifying Turkish and international title matches.
  - Implement core provider search & link resolvers for top providers (HDFilmCehennemi, Dizilla, FilmModu, FilmMakinesi, InatBox, FullHDFilm).

- [ ] **Task 4: Concurrent Stream Aggregator & TV Box Mode** (Est: 5m)
  - Implement `StreamAggregator.kt` with coroutines, `SupervisorJob`, timeout (6s), and `Semaphore(3)` for TV Box mode.
  - Wire into `WioSinemaProvider.kt` (`loadMainPage`, `search`, `load`, `loadLinks`).

- [ ] **Task 5: UI & Settings Dialog** (Est: 4m)
  - Implement `WioSinemaPlugin.kt` with TV Box mode toggle, provider selector popup, and standard `SupportNotice.kt` dialog.
  - Add WioSinema banner/logo asset.

- [ ] **Task 6: Build Verification & Deployment** (Est: 4m)
  - Run `./gradlew :WioSinema:testDebugUnitTest :WioSinema:make`.
  - Install and verify on local test environment / device (`127.0.0.1:16384`).
