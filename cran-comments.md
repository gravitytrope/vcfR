
## Test environments
* local: ubuntu 16.04 LTS and R 3.6.2
* local: OS X Catalina 10.15.2 and R 3.6.2 and clang8
* travis-ci: ubuntu 16.04 LTS, R 3.6.2 and R Under development (unstable) (2020-01-03 r77628)
* AppVeyor: Windows Server 2012 R2 x64 (build 9600) R version 3.6.2 Patched (2020-01-03 r77629)
* winbuilder: R version 3.6.2 (2019-12-12)
* winbuilder: R Under development (unstable) (2020-01-03 r77630)


## R CMD check results
There were no ERRORs.

On Mac there was one WARNINGs.

* checking top-level files ... WARNING
Conversion of ‘README.md’ failed:
pandoc: Could not fetch http://www.r-pkg.org/badges/version/vcfR
TlsExceptionHostPort (HandshakeFailed (Error_Misc "user error (unexpected type received. expecting handshake and got: Alert [(AlertLevel_Fatal,HandshakeFailure)])")) "www.r-pkg.org" 80

I copied and pasted the url into firefox and it worked for me.

There was 1 NOTE:

* checking CRAN incoming feasibility ... NOTE
Maintainer: 'Brian J. Knaus <briank.lists@gmail.com>'

Version contains large components (1.9.0)

Found the following (possibly) invalid URLs:
  URL: http://www.1000genomes.org/node/101
    From: inst/doc/intro_to_vcfR.html
    Status: Error
    Message: libcurl error code 60:
      	SSL certificate problem: unable to get local issuer certificate
      	(Status without verification: OK)

This link does appear to work.

## Downstream dependencies

I have also run R CMD check on downstream dependencies of vcfR
All packages that I could install passed:

devtools::revdep_check() is no longer a part of devtools and the package revdepcheck (on GitHub but not CRAN) threw an error because a dependent R package could not be installed.

I used:
R CMD check --as-cran
on the tarballs from CRAN for the following packages.

Reverse imports: 	binmapr, pcadapt, whoa
Reverse suggests: 	LDheatmap, onemap, perfectphyloR, rehh, SimRVSequences

I spent an entire afternoon trying to install dependencies of reversedependencies of vcfR but was not successful.
It appears there are dependencies of these packages that are not available for R version 3.6.2.


Results:

WARNINGS were thrown because the version tested was the same as on CRAN.

binmapr
* checking Rd cross-references ... NOTE
Package unavailable to check Rd xrefs: ‘qtl’

pcadapt
* checking package dependencies ... ERROR
Packages required but not available:
  'mmapcharr', 'plotly', 'robust', 'RSpectra', 'rmio'

These do not appear to be available for R version 3.6.2.

LDheatmap
Warning message:
package ‘snpStats’ is not available (for R version 3.6.2) 

onemap
package ‘MDSmap’ is not available (for R version 3.6.2)

## Thank you CRAN Core Team!

[CRAN Repository Policy](https://cran.r-project.org/web/packages/policies.html) states that all correspondence should be with CRAN and not members of the team.
However, I think its polite to thank those who have helped this project.
So I've decided to start a list of thanks with the hope that these individuals may see this in the future.

v1.8.0 Thank you Uwe Ligges for processing my submission!

v1.7.0 Thank you Uwe Ligges for processing my submission!

v1.6.0 Thank you Uwe Ligges for processing my submission!

v1.5.0 Thank you Kurt Hornik for helping me!

v1.4.0 Thank you Uwe Ligges and Kurt Hornik for helping me!

v1.3.0 Thank you Uwe Ligges and Kurt Hornik for helping me!
Prof Brian Ripley brought to my attention that I had new memory access issues.
Thank you again for bringing these to my attention!

v1.2.0 Thank you Uwe Ligges for helping me!
This version was accepted on the first try.
See Uwe, I'm learning!

Prof. Brian Ripley also brought to my attention that I had overlooked memory-access errors and that valgrind was reporting use of uninitialized memory and many small memory leaks.
Thank you for bringing this to my attention, its a big help for those of us who are still learning valgrind!

v1.1.0 Thank you Uwe Ligges for helping me get my title in title case, my Description in order and handling my submission!

