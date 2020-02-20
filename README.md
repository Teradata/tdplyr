# tdplyr - Teradata R Package

## Overview

The Teradata R package (tdplyr) combines the benefits of open source R language environment with the
massive parallel processing capabilities of Teradata Vantage, which includes the Teradata Machine
Learning Engine analytic functions and the Teradata NewSQL Engine in-database analytic functions.
It allows users to develop and run R programs that take advantage of the Big Data and
Machine Learning analytics capabilities of Vantage.

This package interface makes available to R users a collection of functions for analytics that reside on
Vantage, so that they can perform in-database analytics with no SQL coding required. Specifically, the
Teradata R package provides functions for data manipulation and transformation, data filtering and sub-setting,
on remote Teradata database table and can be used in conjunction with open source R capabilities. Moreover, 
the Teradata R package conforms and works with the functions of the [dbplyr](https://cran.r-project.org/web/packages/dbplyr/index.html) package and most of the verbs of 
the [dplyr](https://cran.r-project.org/web/packages/dplyr/index.html) package.

Teradata Vantage Client R Analytic library  
Copyright © 2018, Teradata. All Rights Reserved.

For Teradata R package documentation, please visit [Teradata R Package Documentation](https://docs.teradata.com/search/books?filters=prodname~%2522Teradata+R+Package%2522)

For Teradata customer support, please visit [Teradata Access](https://access.teradata.com)

General product information is available in the [Teradata Documentation website](https://docs.teradata.com/)
- Teradata R Package User Guide – B700-4005 
- Teradata R Function Reference – B700-4007
- Teradata&reg; Vantage Machine Learning Engine Analytic Function Reference - B700-4003
- Teradata&reg; Database Analytic Functions - B035-1206

## Installation
The Teradata R package (tdplyr) contains proprietary code and cannot be offered on CRAN. It is available from Teradata's 
R package repository. 

The Teradata R package depends on the rlang, dplyr, dbplyr, DBI, magrittr and teradatasql packages which are available from
CRAN and Teradata's R package repository.

To download and install dependencies automatically, specify the Teradata R package repository and CRAN in the 
`repos` argument for `install.packages`.

```
Rscript -e "install.packages('tdplyr',repos=c('https://teradata-download.s3.amazonaws.com','https://cloud.r-project.org'))"
``` 
 
## Minimum System Requirements

R: (64 bit only)
- R v3.4.3 or later versions

Teradata Vantage:
- Vantage 1.0 - Maintenance Update 2 or later versions
- NewSQL Engine 16.20 Feature Update 1 or later versions
- Teradata Machine Learning Engine 08.00.03.00 or later versions
 
Supported Drivers:
- Teradata SQL Driver for R v16.20.0.34 (Recommended) or later versions
- Teradata ODBC Driver 16.20 (Deprecated)
 
Operating Systems: (64-bit only)
- Windows 7
- MacOS OSX 10.9
- Ubuntu 16
- RHEL 7
- SLES/OpenSUSE 12

## Change Log

#### tdplyr 16.20.00.06
- Compatible with Vantage 1.1.1.\
The following ML Engine functions have new and/or updated arguments to support the Vantage version:
    - `td_adaboost_predict_mle()`
    - `td_decision_forest_predict_mle()`
    - `td_decision_tree_predict_mle()`
    - `td_glm_predict_mle()`
    - `td_lda_mle()`
    - `td_naivebayes_predict_mle()`
    - `td_naivebayes_textclassifier_predict_mle()`
    - `td_svm_dense_predict_mle()`
    - `td_svm_sparse_mle()`
    - `td_svm_sparse_predict_mle()`
    - `td_xgboost_predict_mle()`
- Added support to use generic predict function for `td_adaboost_predict_mle()`. Now `td_adaboost_predict_mle` can be called using `predict(<td_adaboost_mle_obj>, ...)`.

#### tdplyr 16.20.00.05
- Improvements
    - Improved performance when using output of analytic functions as input to dplyr verbs or `copy_to`.
    - Support added to load time series Primary Time Index (PTI) tables using `copy_to()`.
    - Added more examples and updated documentation for some APIs.
- New features/functions
    - tdplyr in conjunction with Teradata SQL Driver for R supports integration with RStudio Connections Pane for exploring the data source once connection is established with Vantage. Please refer the [link](https://db.rstudio.com/rstudio/connections/) for more information about RStudio Connection Pane.
    - `td_fastload()` - for high performance data loading of large amount of data into a table in Teradata Vantage.
    - `td_sample()` - to sample proportion of data.
    - Time series functions
        - `group_by_time()` - to group tbl_terdata object based on time.
        - Time series aggregate functions - to perform aggregate operations on time series tbl_teradata objects grouped by time. Please refer the vignette `time_series_aggregates` for usage.
            - `ts.bottom()`
            - `ts.top()`
            - `ts.first()`
            - `ts.last()`
            - `ts.mad()`
            - `ts.median()`
            - `ts.mode()`
    - `summarise()` - to summarise the tbl_teradata object using both regular and time series aggregate operations.
    - Added a new SQL translation function `as.Date()` which typecasts character data type column to SQL DATE data type column. Please refer the vignette `sql-translation` for usage.
    - Added 10 new MLEngine analytic functions.
        - `td_adaboost_mle`
        - `td_adaboost_predict_mle`
        - `td_glml1l2_mle`
        - `td_glml1l2_predict_mle`
        - `td_pos_tagger_mle`
        - `td_text_chunker_mle`
        - `td_text_classifier_evaluator_mle`
        - `td_text_classifier_mle`
        - `td_text_classifier_trainer_mle`
        - `td_text_morph_mle`

#### tdplyr 16.20.00.04
- Added 4 new SQLEngine analytic functions, which will work only with Vantage 1.1.
    - `td_antiselect_sqle`
    - `td_pack_sqle`
    - `td_string_similarity_sqle`
    - `td_unpack_sqle`

#### tdplyr 16.20.00.03
- Support for Teradata SQL driver for R has been added. Teradata recommends to use Teradata SQL driver for R with tdplyr. 
- Simplified procedure to install tdplyr package with its dependent packages including Teradata SQL driver for R.
- Support added to td_create_context(connect to Teradata Vantage) to support different logon mechanisms with Teradata SQL Driver. Logon mechanisms supported are: TD2, LDAP, TDNEGO, KRB5(for Kerberos).
- 11 new analytic function (9 for MLEngine and 2 for SQLEngine) wrappers have been added.
- Below ML Engine analytic functions have new arguments added and the new arguments will work only with Teradata Vantage 1.1 or later releases.
    - `td_decision_forest_mle`
    - `td_decision_tree_mle`
    - `td_knn_mle`
    - `td_varmax_mle`


#### tdplyr 16.20.00.02
- 45 new Analytic functions added. The package now has 105 analytic functions(9 SQLEngine and 96 MLEngine functions)
- Enhanced copy_to function to have "append" option.
- Updated analytic function names to contain information about the execution engine. Analytic function names will have "_sqle" or "_mle" extension in the function names.
- Configurable aliases for Analytic functions


#### tdplyr 16.20.00.01
- Initial release of Teradata R package for analytics within Teradata Vantage
- Provide compatibility with dplyr package verbs for a SQL-like grammar via R functions for data manipulation
- Provides compatibility with dbplyr package which provides a database backend for R and enables using remote database tables as in-memory R data frames 
- Supports connectivity to Teradata database using Teradata ODBC driver
- Provides R interface to run MLEngine and SQLEngine analytic functions within Teradata Vantage
- Support for 3 major OS Platforms(Windows/OSX/Linux)
