<!-- badges: start -->
[![R-CMD-check](https://github.com/NewGraphEnvironment/fpr/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/NewGraphEnvironment/fpr/actions/workflows/R-CMD-check.yaml)
<!-- badges: end -->


Package used for building [interactive reports]((https://newgraphenvironment.github.io/fish_passage_skeena_2021_reporting/)) related to fish passage planning including fish passage assessments and habitat confirmation assessments at road-stream crossings.  

<br>

Currently under active development and likely to change significantly. Honestly likely only useful for me at this point unless you want to disect each function to understand things like the folder structure of the repo used to build the actual report. Likely to evolve into several smaller packages and definitely needs more documentation.  Just a start here.  Use at your own risk and consider keeping track of which version of the package you are using through the date formatted tags. Many of these notes are for me to remember what is going on...

<br>

Install with `devtools::install_github("NewGraphEnvironment/fpr")`

<br>

If looking for backwards comparability because you used the package in the past and there are issues now with a newer release of the package, install with:

`devtools::install_github("NewGraphEnvironment/fpr", ref = "v1.0.0")` (tag coinciding with the one you used to report)

<br>

The reporting that this package serves to help line up is generated with `bookdown` from `Rmarkdown` so there are many dependencies such as `knitr` and `KableExtra`. Additionally, of key importance workflows rely on provincial British Columbia data input spreadsheets with version updates.  As of 2022-04-13 the provincial templates included:

 + Populated [Fish Data Submission Spreadsheet Template - V 2.0, January 20, 2020 ](https://www2.gov.bc.ca/gov/content/environment/plants-animals-ecosystems/fish/fish-and-fish-habitat-data-information/fish-data-submission/submit-fish-data#submitfish) 

 + Populated [pscis_assessment_template_v24.xls](https://www2.gov.bc.ca/gov/content/environment/plants-animals-ecosystems/fish/aquatic-habitat-management/fish-passage/fish-passage-technical/assessment-projects)
 
 <br>
 
 
Additionally many outputs manipulated by these functions rely on a tables generated from a `postgresql` database built with [`bcfishpass`](https://github.com/smnorris/bcfishpass). Some tables are unstable with column names likely to change in the future.

<br>

Custom inputs include:

 + Custom CSV file [example here](https://github.com/NewGraphEnvironment/fish_passage_skeena_2021_reporting/blob/master/data/habitat_confirmations_priorities.csv) detailing Phase 2 site:
     - priority level for proceeding to design for replacement
     - length of survey upstream and downstream
     - a conservative estimate of the linear length of mainstem habitat potentially available upstream of the crossing 
     - fish species confirmed as present upstream of the crossing following assessments.


 + Photos within structured folders and naming conventions as per the Provincial Stream Crossing Information System and project specific protocols [example here](https://github.com/NewGraphEnvironment/fish_passage_skeena_2021_reporting/tree/master/data/photos) 
