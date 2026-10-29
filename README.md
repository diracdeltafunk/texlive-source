# diracdeltafunk/texlive-source

A fork of [TeX-Live/texlive-source](https://github.com/TeX-Live/texlive-source)
for preparing patches. The code lives on `trunk` (a mirror of upstream) and on
feature branches.

This default branch, `fork-ci`, holds only
[`.github/workflows/fork-ci.yml`](.github/workflows/fork-ci.yml). That workflow
builds a branch and runs its tests on GNU/Linux (x86_64, i386, musl, aarch64,
armhf, and s390x if requested), FreeBSD, macOS (arm64, x86_64), and Windows
(MSYS2 MinGW-w64) before the branch is proposed upstream:

```sh
gh workflow run fork-ci.yml -R diracdeltafunk/texlive-source -f ref=BRANCH
```

Add `-f scope=full` to build everything `./Build` builds instead of only
kpathsea, TeX, e-TeX and pdfTeX. Windows and s390x always use the pdfTeX-only
build.
