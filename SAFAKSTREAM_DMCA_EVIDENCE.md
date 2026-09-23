# SafakStream DMCA Evidence Report

**Prepared:** 2026-09-23  
**Copyright claimant / repositories:** GitHub user `Wiojelt`  
**Reported repository:** https://github.com/SafakStream/SafakStream

## Scope of this report

This report is limited to code and integration layers authored/maintained in the Wiojelt projects, including the Wio/TurkSinema entry and common infrastructure and the TurkSpor common/shared infrastructure. It does **not** claim ownership of third-party upstream provider code merely because that provider also appears in a Wiojelt repository.

Relevant claimant repositories:

- https://github.com/Wiojelt/WioSinema
- https://github.com/Wiojelt/TurkSinema
- https://github.com/Wiojelt/TurkSpor
- Private source repositories available to GitHub for verification: `Wiojelt/TurkSinema-Source` and `Wiojelt/TurkSpor-Source`

The public Wiojelt repositories are licensed under GNU GPL v3. The reported SafakStream repository currently exposes only `master` and `builds` branches. As of 2026-09-23, I could not identify a GPL license file, corresponding source code for the derivative binaries listed below, or a source-code offer in the reported repository. The reported repository distributes compiled `.cs3` binaries.

## Strong direct evidence

### 1. ClipBox

Claimant distribution:
- https://github.com/Wiojelt/WioSinema/blob/builds/ClipBox.cs3

Reported binary:
- https://github.com/SafakStream/SafakStream/blob/builds/ClipBox.cs3

SafakStream's own `plugins.json` identifies this binary with:

`pluginClassName = dev.wiojelt.turksinema.entry.ClipBoxEntry`

The SafakStream binary's `classes.dex` also contains `dev/wiojelt/turksinema`, `ClipBoxEntry`, and Wiojelt common support classes.

The corresponding claimant source entry exists at:

`ClipBox/src/main/kotlin/dev/wiojelt/turksinema/entry/ClipBoxEntry.kt`

in the private source repository `Wiojelt/TurkSinema-Source`.

SafakStream metadata simultaneously changes the author to `SafakStream`.

### 2. DiziMom

Claimant distribution:
- https://github.com/Wiojelt/WioSinema/blob/builds/DiziMom.cs3

Reported binary:
- https://github.com/SafakStream/SafakStream/blob/builds/DiziMom.cs3

The reported binary contains, among others:

- `Ldev/wiojelt/turksinema/entry/DiziMomEntry;`
- `Ldev/wiojelt/turksinema/common/DomainUpdateUi;`
- `Ldev/wiojelt/turksinema/common/SupportNotice;`

The corresponding claimant source entry is:

`DiziMom/src/main/kotlin/dev/wiojelt/turksinema/entry/DiziMomEntry.kt`

### 3. HDFilmCehennemi

Claimant distribution:
- https://github.com/Wiojelt/WioSinema/blob/builds/HDFilmCehennemi.cs3

Reported binary:
- https://github.com/SafakStream/SafakStream/blob/builds/HDFilmCehennemi.cs3

The reported binary contains Wiojelt common infrastructure, including:

- `dev/wiojelt/turksinema/common/SupportNotice`
- `dev/wiojelt/turksinema/common/DomainUpdateUi`
- `dev/wiojelt/turksinema/common/WioSettingsConfig`

The corresponding claimant entry source is:

`HDFilmCehennemi/src/main/kotlin/dev/wiojelt/turksinema/entry/HDFilmCehennemiEntry.kt`

### 4. Sinemakolik

Claimant distribution:
- https://github.com/Wiojelt/WioSinema/blob/builds/Sinemakolik.cs3

Reported binary:
- https://github.com/SafakStream/SafakStream/blob/builds/Sinemakolik.cs3

The reported binary contains:

- `Ldev/wiojelt/turksinema/entry/SinemakolikEntry;`
- `Ldev/wiojelt/turksinema/common/DomainUpdateUi;`
- `Ldev/wiojelt/turksinema/common/SupportNotice;`
- additional `com/wiojelt/turkstream/sinemakolik` package paths

The corresponding claimant source entry is:

`Sinemakolik/src/main/kotlin/dev/wiojelt/turksinema/entry/SinemakolikEntry.kt`

## TurkSpor-derived binaries

The following reported SafakStream binaries contain compiled classes/string references matching the claimant's TurkSpor common/shared infrastructure, including combinations of:

- `turkspor/common/SourceCredit`
- `SourceCredits`
- `SourceSpec`
- `DomainResolver`
- `ChannelArtwork`
- `SupportNotice`

The claimant's original infrastructure exists in `Wiojelt/TurkSpor-Source`, including:

- `common/src/main/kotlin/turkspor/common/SupportNotice.kt`
- `common/src/main/kotlin/turkspor/common/SourceCredits.kt`
- `shared/src/main/kotlin/turkspor/shared/SourceSpec.kt`
- `shared/src/main/kotlin/turkspor/shared/DomainResolver.kt`
- `shared/src/main/kotlin/turkspor/shared/ChannelArtwork.kt`

Affected reported binaries:

| Reported SafakStream file | Claimant counterpart | Evidence found in reported binary |
|---|---|---|
| https://github.com/SafakStream/SafakStream/blob/builds/BeyazElma.cs3 | https://github.com/Wiojelt/TurkSpor/blob/builds/BeyazElma.cs3 | `turkspor`, `SupportNotice`, `SourceCredits`, `SourceSpec`, `DomainResolver`, `ChannelArtwork` |
| https://github.com/SafakStream/SafakStream/blob/builds/TRGoals.cs3 | https://github.com/Wiojelt/TurkSpor/blob/builds/TRGoals.cs3 | `Lturkspor/common/SourceCredit;`, `SupportNotice`, `SourceCredits`, `SourceSpec`, `DomainResolver`, `ChannelArtwork` |
| https://github.com/SafakStream/SafakStream/blob/builds/PapazSports.cs3 | https://github.com/Wiojelt/TurkSpor/blob/builds/PapazSports.cs3 | same TurkSpor common/shared infrastructure; description text also matches claimant package |
| https://github.com/SafakStream/SafakStream/blob/builds/NetVGold.cs3 | https://github.com/Wiojelt/TurkSpor/blob/builds/NetVGold.cs3 | `turkspor`, `SupportNotice`, `SourceCredits`, `SourceSpec`, `DomainResolver`, `ChannelArtwork` |
| https://github.com/SafakStream/SafakStream/blob/builds/DominoTV.cs3 | https://github.com/Wiojelt/TurkSpor/blob/builds/DominoTV.cs3 | `turkspor`, `wiojelt`, `SupportNotice`, `SourceCredits` |
| https://github.com/SafakStream/SafakStream/blob/builds/InatTV.cs3 | https://github.com/Wiojelt/TurkSpor/blob/builds/InatTV.cs3 | `turkspor`, `SupportNotice`, `SourceCredits`, `DomainResolver`, `ChannelArtwork` |
| https://github.com/SafakStream/SafakStream/blob/builds/AslanTV.cs3 | https://github.com/Wiojelt/TurkSpor/blob/builds/AslanTV.cs3 | `turkspor`, `wiojelt`, `SupportNotice`, `SourceCredits`, `SourceSpec`, `DomainResolver`, `ChannelArtwork` |
| https://github.com/SafakStream/SafakStream/blob/builds/SelcukSports.cs3 | https://github.com/Wiojelt/TurkSpor/blob/builds/SelcukSports.cs3 | `turkspor`, `SupportNotice`, `SourceCredits`, `DomainResolver`, `ChannelArtwork` |

### BeyazElma metadata link

SafakStream's current plugin metadata lists `authors: ["SafakStream"]`, while its icon URL still directly points to:

`https://raw.githubusercontent.com/Wiojelt/TurkSpor/main/assets/providers/BeyazElma.png`

This is an additional direct technical link between the repackaged SafakStream entry and the claimant repository.

## SafakStreamTV bundle

Reported bundle:
- https://github.com/SafakStream/SafakStream/blob/builds/SafakStreamTV.cs3

The bundle's `classes.dex` contains all of the following categories simultaneously:

- `dev/wiojelt`
- `turksinema`
- `turkspor`
- `SupportNotice`
- `SourceCredits`
- `DomainResolver`
- `SourceSpec`
- `ChannelArtwork`

Examples include `Lturkspor/common/SourceCredit;` and `Lturkspor/shared/CatalogueController;`.

This indicates that rebranding the bundle as `SafakStreamTV` did not remove the copied Wiojelt/TurkSpor/TurkSinema compiled infrastructure.

## Chronology examples

The claimant's public build history predates the reported copies in multiple cases.

- `Wiojelt/TurkSpor` had `BeyazElma.cs3` in the builds history by 2026-08-31. SafakStream's first observed addition of `BeyazElma.cs3` is 2026-09-21.
- `Wiojelt/TurkSpor` had `TRGoals.cs3` in the builds history by 2026-09-05. SafakStream added it on 2026-09-21.
- `Wiojelt/TurkSpor` had `PapazSports.cs3` in the builds history by 2026-09-06. SafakStream added it on 2026-09-21.

## Reproduction method

The `.cs3` packages are ZIP containers. The findings above can be reproduced by extracting `classes.dex` and inspecting its strings/class descriptors.

Example workflow:

```text
unzip <plugin>.cs3
strings classes.dex | grep -Ei 'dev/wiojelt|turksinema|turkspor|SupportNotice|SourceCredits|SourceSpec|DomainResolver|ChannelArtwork'
```

For ClipBox, the Wiojelt class name is additionally visible directly in SafakStream's published `plugins.json`, without decompilation.

Reported plugin manifest:
- https://github.com/SafakStream/SafakStream/blob/builds/plugins.json

## License / authorization issue

The Wiojelt public projects are distributed under GNU GPL v3. This complaint is not based on the proposition that GPL software can never be redistributed. The issue is that the reported repository is distributing derivative compiled binaries containing the claimant's original integration/common infrastructure while, as currently published, I could not identify corresponding source code, a GPL license/copying notice, or a source-code offer for these derivatives in the reported repository.

This report is therefore limited to the claimant's copyrightable original contributions and the conditions governing authorized redistribution of those contributions. It does not claim exclusive rights over unrelated third-party upstream provider code.

## Requested remediation

Remove the following reported binaries and their entries from `plugins.json`, and remove the same copied classes from any aggregate bundle such as `SafakStreamTV.cs3`:

- ClipBox.cs3
- DiziMom.cs3
- HDFilmCehennemi.cs3
- Sinemakolik.cs3
- BeyazElma.cs3
- TRGoals.cs3
- PapazSports.cs3
- NetVGold.cs3
- DominoTV.cs3
- InatTV.cs3
- AslanTV.cs3
- SelcukSports.cs3
- SafakStreamTV.cs3

Alternatively, any continued distribution must fully satisfy the applicable GPLv3 requirements for the claimant's GPL-licensed code, including corresponding source and applicable notices/license obligations.
