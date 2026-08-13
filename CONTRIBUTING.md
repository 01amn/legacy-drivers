# Contributing to legacy-drivers

Thank you for helping preserve historical Linux printer drivers.

The goal of this repository is to preserve **original upstream
printer-driver projects** that are old, abandoned, difficult to find, or
at risk of disappearing.

Please follow the process below before adding a driver.

## 1. Find a candidate driver

Look for historical printer drivers in places such as:

-   old Linux software archives
-   historical FTP mirrors
-   old distribution archives
-   project websites
-   Internet Archive / Wayback Machine
-   old CDs or software collections
-   source archives referenced by old packages

A candidate should be related to printer support and should have
identifiable source code.

Do not start by rewriting, modernizing, or fixing the driver.

The first goal is **preservation and provenance**.

------------------------------------------------------------------------

## 2. Find the original upstream source

Try to identify where the driver originally came from.

Record:

-   Original project name
-   Original author(s), if known
-   Original project/homepage URL
-   Original download URL
-   Original FTP location, if applicable
-   Original version
-   Original release date
-   Original archive filename
-   Any historical mirrors
-   Wayback Machine URLs, when useful

For example:

``` text
Project: Example Printer Driver
Version: 0.8.9
Archive: example089.tgz
Release date: 1996-03-15
Original URL: http://example.org/example089.tgz
```

A distribution package is useful evidence, but **a distribution package
is not automatically the original upstream source**.

------------------------------------------------------------------------

## 3. Establish source provenance

Before proposing the driver, compare the historical source with later
copies.

Useful sources include:

-   original upstream archives
-   Wayback snapshots
-   Debian source packages
-   Ubuntu source packages
-   Fedora/RPM packages
-   other historical distributions

Try to determine:

``` text
Original upstream
       ↓
Historical release
       ↓
Distribution copies
       ↓
Later maintenance / patches
```

Clearly separate:

1.  **Original upstream code**
2.  **Distribution changes**
3.  **Third-party patches**
4.  **Your own changes**

Do not mix these together.

If a modern distribution still ships the driver, that does **not**
automatically mean the original upstream project is still active.

------------------------------------------------------------------------

## 4. Check whether upstream is abandoned

This is an important step.

Find evidence showing the status of the original upstream project.

Look for:

-   last upstream release
-   last upstream website update
-   last upstream source release
-   old mailing-list activity
-   old development announcements
-   project closure notices
-   absence of newer upstream releases
-   whether only distributions continue carrying the code

Be careful with the distinction:

> **A driver can be abandoned upstream while still being packaged by
> Linux distributions.**

For example:

``` text
Upstream project stops development
             ↓
       Debian keeps it
             ↓
       Ubuntu keeps it
             ↓
 Other distributions keep it
```

Distribution maintenance alone does not prove active upstream
development.

------------------------------------------------------------------------

## 5. Check the license

Inspect the **original upstream archive**, not only a modern
distribution package.

Look for:

-   LICENSE
-   COPYING
-   README
-   source-file copyright headers
-   distribution terms
-   public-domain statements
-   author permission

Record the exact license information and where it was found.

If the license is unclear, **do not assume that the source is freely
redistributable**.

Raise the issue for review.

------------------------------------------------------------------------

## 6. Preserve the original source

The default rule is:

> **Preserve first. Modify later, and only when there is a clear
> reason.**

Keep the original source as close as possible to the historical upstream
release.

Do not:

-   rewrite the driver
-   automatically format all source files
-   rename files without a reason
-   remove old files because they look unnecessary
-   replace the original build system
-   silently apply distribution patches
-   change copyright notices
-   change the license

If build fixes or other changes are necessary, keep them separate and
document them clearly.

------------------------------------------------------------------------

## 7. Verify the archive

Record useful integrity and identification information.

For example:

``` text
Filename: cjet089.tgz
Version: 0.8.9
Date: 1996-03-15
SHA256: <hash>
```

If several historical copies exist, compare them.

A matching hash is strong evidence that two copies contain exactly the
same archive.

If they differ, investigate why.

------------------------------------------------------------------------

## 8. Inspect the source before building

Look at the contents of the archive.

Check for:

-   README
-   INSTALL
-   COPYING / LICENSE
-   Makefile
-   ChangeLog
-   source files
-   example configuration
-   printer-specific files
-   documentation
-   test programs
-   sample input/output

Do not remove files simply because they appear outdated.

Historical files may be important for provenance.

------------------------------------------------------------------------

## 9. Test buildability

Try to build the **original source first**.

Document:

-   operating system
-   compiler
-   required libraries/tools
-   build command
-   build result
-   compiler errors
-   warnings
-   missing dependencies

For example:

``` text
Environment:
  Debian GNU/Linux
  GCC

Command:
  make

Result:
  Does not build with modern GCC.

Reason:
  Old C syntax rejected by modern compiler.
```

Build failure does not automatically disqualify a historical driver.

The purpose of this step is to document its current state.

------------------------------------------------------------------------

## 10. Do not silently fix historical code

If the original driver does not build, do not immediately modify it.

First record the failure.

If a compatibility patch is useful, keep it clearly separate:

``` text
upstream/
    original historical source

patches/
    modern-build-fix.patch
```

The original source should remain recoverable.

------------------------------------------------------------------------

## 11. Check for existing copies in legacy-drivers

Before opening a pull request, search this repository.

Check:

-   driver name
-   archive name
-   version
-   author
-   source files
-   printer models
-   historical URLs

Avoid creating duplicate copies of the same upstream project.

If you find a related driver already present, explain why your candidate
is different.

------------------------------------------------------------------------

## 12. Prepare a provenance record

Before proposing the driver, collect the evidence in one place.

Use a structure like:

``` text
Driver:
Version:
Archive:
Release date:

Original author:
Original project:
Original URL:
Original download URL:

Historical mirrors:

Wayback references:

License:
License location:

Last known upstream release:
Evidence of abandonment:

Distribution copies:
Debian:
Ubuntu:
Fedora/RPM:
Other:

Build status:
Build environment:
Build command:

SHA256:

Notes:
```

This makes review much easier.

------------------------------------------------------------------------

## 13. Open an issue before adding uncertain drivers

If the provenance, license, or upstream status is unclear, open an issue
first.

Explain:

-   what you found
-   why it appears to be a historical printer driver
-   where the original source was found
-   what evidence connects the copies
-   what is still uncertain

Ask maintainers whether the candidate fits the repository.

Do not assume that every old printer-related program belongs in
`legacy-drivers`.

------------------------------------------------------------------------

## 14. Create the pull request

Once the candidate is sufficiently verified:

1.  Preserve the original source.
2.  Add provenance information.
3.  Add checksums where appropriate.
4.  Document the source URL and historical evidence.
5.  Document the license.
6.  Document buildability.
7.  Clearly identify any patches.
8.  Explain why the driver belongs in `legacy-drivers`.

The pull request description should allow a maintainer to understand
**where the driver came from and why it should be preserved** without
repeating the entire investigation.

------------------------------------------------------------------------

# What makes a good legacy-driver candidate?

A strong candidate usually has several of these characteristics:

-   Historical Linux printer driver
-   Original upstream source can be identified
-   Old release with clear provenance
-   Upstream project is abandoned or no longer maintained
-   Source is at risk of disappearing
-   License permits preservation/redistribution
-   Original source can be separated from later distribution patches
-   Historical documentation is available
-   The driver has genuine historical value

------------------------------------------------------------------------

# Important distinction: upstream vs distribution maintenance

This repository is interested in preserving historical **upstream
projects**, not simply copying whatever source is currently packaged by
a distribution.

For example:

``` text
Historical upstream source
          │
          ├── Debian patches
          ├── Ubuntu patches
          ├── Fedora patches
          └── Other distribution changes
```

Whenever possible, preserve the upstream source separately from those
downstream changes.

A driver being present in Debian or Ubuntu today does not by itself
prove that its original upstream project is active.

------------------------------------------------------------------------

# Example investigation

Suppose you find:

``` text
cjet089.tgz
dated: 1996-03-15
```

Do not immediately add it.

Investigate:

``` text
1. Where did cjet originate?
          ↓
2. Who wrote it?
          ↓
3. Is cjet089.tgz the original upstream archive?
          ↓
4. What is the original URL?
          ↓
5. Can Wayback confirm the history?
          ↓
6. What is the original license?
          ↓
7. What was the final upstream release?
          ↓
8. When did upstream development stop?
          ↓
9. Are modern Debian/Ubuntu copies derived from it?
          ↓
10. Can the original source be built?
          ↓
11. Preserve the original source
          ↓
12. Open issue / PR
```

This is the preferred investigation pattern.

------------------------------------------------------------------------

# What not to do

### Do not start by modernizing

Bad approach:

``` text
Find old driver
    ↓
Rewrite code
    ↓
Make it compile
    ↓
Add modified version
```

Preferred approach:

``` text
Find old driver
    ↓
Find original upstream
    ↓
Verify provenance
    ↓
Verify license
    ↓
Verify abandonment
    ↓
Preserve original source
    ↓
Document build status
    ↓
Only then consider separate fixes
```

### Do not treat package repositories as upstream automatically

A Debian or Ubuntu source package may contain:

-   upstream source
-   Debian/Ubuntu patches
-   packaging files
-   build fixes
-   distribution-specific changes

Always identify which files came from upstream.

### Do not remove old files

A file may look useless today but still be valuable evidence of the
original project.

When in doubt, preserve it and discuss removal with maintainers.

------------------------------------------------------------------------

# Contributor checklist

Before opening a PR, make sure you can answer these questions:

-   [ ] What is the driver's name?
-   [ ] What is the original version?
-   [ ] What is the original archive filename?
-   [ ] What is the original release date?
-   [ ] Who was the original author?
-   [ ] What was the original project URL?
-   [ ] What was the original download URL?
-   [ ] Did I check historical mirrors?
-   [ ] Did I check Wayback history?
-   [ ] Did I establish source provenance?
-   [ ] Did I distinguish upstream source from distribution patches?
-   [ ] Did I determine the original license?
-   [ ] Did I verify that the license permits preservation?
-   [ ] Did I investigate the last upstream release?
-   [ ] Did I investigate whether upstream is abandoned?
-   [ ] Did I check whether distributions still package it?
-   [ ] Did I compare available source copies?
-   [ ] Did I calculate a checksum?
-   [ ] Did I inspect the original archive contents?
-   [ ] Did I try building the original source?
-   [ ] Did I document build failures?
-   [ ] Did I keep the original source untouched?
-   [ ] Did I search `legacy-drivers` for duplicates?
-   [ ] Did I document all important provenance evidence?
-   [ ] If anything is uncertain, did I discuss it with maintainers
    before adding it?

------------------------------------------------------------------------

# Guiding principle

**The purpose of `legacy-drivers` is preservation, not modernization.**

When investigating an old driver, think like an archivist:

> **Find it → identify its origin → verify its history → verify its
> license → separate upstream from downstream changes → preserve the
> original → document what you found.**

A successful contribution should make it possible for someone many years
from now to understand **what this driver was, where it came from, which
version was preserved, and why the preserved source is authentic.**
