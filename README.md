Staggered
=========

The `staggered` package implements xx

`version 0.2.1 09Feb2023` | [Background](#background) | [Installation](#installation) | [Examples](#examples)

## Background

xx

## Installation

The package may be installed by using `net install`:

```stata
local github https://raw.githubusercontent.com
net install staggered, from(`github'/mcaceresb/stata-staggered/main) replace
```

You can also clone or download the code manually, e.g. to
`stata-multe-main`, and install from a local folder:

```stata
cap noi net uninstall multe
net install multe, from(`c(pwd)'/stata-multe-main)
```

## Examples

```stata
use ./test/pj_officer_level_balanced.dta, clear
staggered complaints, i(uid) t(period) g(first_trained) estimand(simple)
ereturn list
staggered, vce(conservative)

staggered complaints, i(uid) t(period) g(first_trained) estimand(cohort)
mata (`e(mata)'.se_conservative, `e(mata)'.se_adjusted)

staggered complaints, i(uid) t(period) g(first_trained) estimand(calendar)
mata (`e(mata)'.se_conservative, `e(mata)'.se_adjusted)
```
