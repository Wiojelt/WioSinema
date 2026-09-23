# GitHub DMCA Takedown Notice Draft — SafakStream

> Use this draft with GitHub's Copyright Claims / DMCA takedown form. Replace all bracketed personal-information placeholders before submitting. Check GitHub's required sworn-statement boxes only if they are true.

## 1. Copyright owner / authority

I am the copyright owner of the original integration, entry-wrapper, settings/support, domain-resolution, source-credit, artwork/catalogue and other common/shared code identified below in my WioSinema/TurkSinema and TurkSpor projects. My GitHub username is Wiojelt.

I am not claiming ownership of unrelated third-party upstream provider code. This notice is limited to my own copyrightable contributions and compiled copies/derivatives of those contributions.

## 2. Copyrighted works

My relevant projects are:

https://github.com/Wiojelt/WioSinema
https://github.com/Wiojelt/TurkSinema
https://github.com/Wiojelt/TurkSpor

The corresponding source repositories are maintained under my GitHub account as Wiojelt/TurkSinema-Source and Wiojelt/TurkSpor-Source and can be made available to GitHub for verification.

My original code includes, among other components:

- dev.wiojelt.turksinema entry wrappers such as ClipBoxEntry, DiziMomEntry, HDFilmCehennemiEntry and SinemakolikEntry;
- dev.wiojelt.turksinema common infrastructure such as SupportNotice, DomainUpdateUi and WioSettingsConfig;
- TurkSpor common/shared infrastructure such as SupportNotice, SourceCredits / SourceCredit, SourceSpec, DomainResolver, ChannelArtwork and CatalogueController.

The public projects are licensed under GNU GPL v3. My complaint does not assert that GPL software can never be redistributed. The reported repository is distributing derivative compiled binaries containing my original GPL-licensed contributions, while I could not identify corresponding source code, the applicable GPL license/copying information, or a source-code offer for these derivatives in the reported repository as of 23 September 2026.

Technical evidence is documented here:

https://github.com/Wiojelt/WioSinema/blob/main/SAFAKSTREAM_DMCA_EVIDENCE.md

## 3. Allegedly infringing repository and files

Reported repository:

https://github.com/SafakStream/SafakStream

I am reporting the following specific compiled files:

https://github.com/SafakStream/SafakStream/blob/builds/ClipBox.cs3
https://github.com/SafakStream/SafakStream/blob/builds/DiziMom.cs3
https://github.com/SafakStream/SafakStream/blob/builds/HDFilmCehennemi.cs3
https://github.com/SafakStream/SafakStream/blob/builds/Sinemakolik.cs3
https://github.com/SafakStream/SafakStream/blob/builds/BeyazElma.cs3
https://github.com/SafakStream/SafakStream/blob/builds/TRGoals.cs3
https://github.com/SafakStream/SafakStream/blob/builds/PapazSports.cs3
https://github.com/SafakStream/SafakStream/blob/builds/NetVGold.cs3
https://github.com/SafakStream/SafakStream/blob/builds/DominoTV.cs3
https://github.com/SafakStream/SafakStream/blob/builds/InatTV.cs3
https://github.com/SafakStream/SafakStream/blob/builds/AslanTV.cs3
https://github.com/SafakStream/SafakStream/blob/builds/SelcukSports.cs3
https://github.com/SafakStream/SafakStream/blob/builds/SafakStreamTV.cs3

The repository's plugin manifest also participates in distribution of these binaries:

https://github.com/SafakStream/SafakStream/blob/builds/plugins.json

I am not alleging that every file in the SafakStream repository infringes. My notice is directed to the specific files listed above, their manifest entries, and copies of the same code embedded in aggregate bundles.

## 4. Explanation of infringement / technical evidence

This is not based merely on similar plugin names.

For example, SafakStream's own published plugin metadata identifies its repackaged ClipBox binary with the class name:

dev.wiojelt.turksinema.entry.ClipBoxEntry

while identifying the author as SafakStream.

Inspection of the distributed classes.dex files also identifies my package/class structure and common code.

Examples include:

- DiziMom: dev/wiojelt/turksinema/entry/DiziMomEntry, DomainUpdateUi, SupportNotice.
- HDFilmCehennemi: dev/wiojelt/turksinema/common/SupportNotice, DomainUpdateUi and WioSettingsConfig.
- Sinemakolik: dev/wiojelt/turksinema/entry/SinemakolikEntry and com/wiojelt/turkstream/sinemakolik package paths.
- BeyazElma, TRGoals, PapazSports, NetVGold, DominoTV, InatTV, AslanTV and SelcukSports contain TurkSpor common/shared classes including combinations of SourceCredit / SourceCredits, SourceSpec, DomainResolver, ChannelArtwork and SupportNotice.
- SafakStreamTV contains both dev/wiojelt / turksinema references and turkspor common/shared infrastructure, including turkspor/common/SourceCredit and turkspor/shared/CatalogueController.

SafakStream's BeyazElma metadata also changes the listed author to SafakStream while still directly referencing an image hosted in my Wiojelt/TurkSpor repository.

The full reproducible evidence, including chronology and the method used to inspect the .cs3 ZIP/classes.dex packages, is here:

https://github.com/Wiojelt/WioSinema/blob/main/SAFAKSTREAM_DMCA_EVIDENCE.md

## 5. Requested remedy

Please require the repository owner to remove the specific reported .cs3 binaries listed above and remove their distribution entries from plugins.json.

SafakStreamTV.cs3 must also be removed or rebuilt so that it no longer contains my copied Wiojelt/TurkSinema/TurkSpor code.

If the repository owner wishes to continue distributing any derivative of my GPLv3-licensed code, the distribution must first be brought into full compliance with the applicable GPLv3 requirements, including corresponding source and applicable license/notices. Until such compliance is established, I request that access to the reported noncompliant copies be disabled.

I am not requesting removal of unrelated files for which I have not identified my copyrighted code.

## 6. Alleged infringer contact

GitHub username / repository owner: SafakStream

Repository:
https://github.com/SafakStream/SafakStream

I do not have additional verified private contact information for the repository owner.

## 7. My contact information

Legal name: [YOUR FULL LEGAL NAME]
Email: [YOUR EMAIL ADDRESS]
Telephone: [YOUR TELEPHONE NUMBER]
Physical address: [YOUR FULL PHYSICAL MAILING ADDRESS]

## 8. Signature

Electronic signature: [YOUR FULL LEGAL NAME]

Date: [DATE OF SUBMISSION]
