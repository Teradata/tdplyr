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
the Teradata R package conforms and works with the functions of the [dbplyr](https://cran.r-project.org/web/packages/dbplyr/index.html) package and 
most of the verbs of the [dplyr](https://cran.r-project.org/web/packages/dplyr/index.html) package.

Teradata Vantage Client R Analytic library  
Copyright © 2018, Teradata. All Rights Reserved.

For Teradata R package documentation, please visit [Teradata R Package Documentation](https://docs.teradata.com/search/books?filters=prodname~%2522Teradata+R+Package%2522)

For Teradata customer support, please visit [Teradata Access](https://access.teradata.com) or email Analytic-Clients Support at <SA230577@teradata.com>.

General product information is available in the [Teradata Documentation website](https://docs.teradata.com/)
- Teradata R Package User Guide – B700-4005 
- Teradata R Function Reference – B700-4007
- Teradata&reg; Vantage Machine Learning Engine Analytic Function Reference - B700-4003
- Teradata&reg; Database Analytic Functions - B035-1206

## Installation
The Teradata R package (tdplyr) contains proprietary code and cannot be offered on CRAN. It is available from Teradata's 
R package repository. 

The Teradata R package depends on `rlang`, `dplyr`, `dbplyr`, `DBI`, `magrittr`, `jsonlite`, `purrr`, `bit64` and `teradatasql`
packages which are available from CRAN or Teradata's R package repository.

To download and install tdplyr along with its dependencies automatically, specify the Teradata R package repository and CRAN in the repos argument for `install.packages`.
```
Rscript -e "install.packages('tdplyr',repos=c('https://r-repo.teradata.com','https://cloud.r-project.org'))"
```

## Minimum System Requirements

R: (64 bit only)
- R v3.4.3 or later versions

Teradata Vantage:
- Vantage 1.0 - Maintenance Update 2 or later versions
- Advanced SQL (was NewSQL) Engine 16.20 Feature Update 1 or later versions
- Teradata Machine Learning Engine 08.00.03.00 or later versions
 
Supported Drivers:
- Teradata SQL Driver for R 17.20.0.19 (Recommended) or later versions
- Teradata ODBC Driver (Deprecated)
 
Operating Systems: (64-bit only)
- Windows 7
- MacOS OSX 10.9
- Ubuntu 16
- RHEL 7
- SLES/OpenSUSE 12

## Change Log

#### tdplyr 17.20.0.0
- New Features/Functions:
  - Support added for following Analytics Database Analytic Functions. 
    - MODEL SCORING functions:
      - `td_glm_predict_per_segment()`
      - `td_kmeans_predict()`
      - `td_one_class_svm_predict()`
      - `td_svm_predict()`
      - `td_glm_predict()`
      - `td_xg_boost_predict()`
    - FEATURE ENGINEERING TRANSFORM functions:
      - `td_antiselect()`
      - `td_bincode_fit()`
      - `td_bincode_transform()`
      - `td_column_transformer()`
      - `td_fit()`
      - `td_non_linear_combine_fit()`
      - `td_non_linear_combine_transform()`
      - `td_one_hot_encoding_fit()`
      - `td_one_hot_encoding_transform()`
      - `td_ordinal_encoding_fit()`
      - `td_ordinal_encoding_transform()`
      - `td_polynomial_features_fit()`
      - `td_polynomial_features_transform()`
      - `td_random_projection_fit()`
      - `td_random_projection_min_components()`
      - `td_random_projection_transform()`
      - `td_row_normalize_fit()`
      - `td_row_normalize_transform()`
      - `td_scale_fit()`
      - `td_scale_transform()`
      - `td_target_encoding_fit()`
      - `td_target_encoding_transform()`
      - `td_transform()`
    - PATH AND PATTERN ANALYSIS functions:
      - `td_attribution()`
      - `td_npath()`
      - `td_sessionize()`
    - SCORING WITH MACHINE LEARNING ENGINE MODELS functions:
      - `td_decision_forest_predict_mle_sqle()`
      - `td_decision_tree_predict_mle_sqle()`
      - `td_glm_predict_mle_sqle()`
      - `td_naivebayes_predict_mle_sqle()`
      - `td_svm_sparse_predict_mle_sqle()`
    - DATA EXPLORATION functions:
      - `td_categorical_summary()`
      - `td_column_summary()`
      - `td_get_rows_with_missing_values()`
      - `td_histogram()`
      - `td_moving_average()`
      - `td_qq_norm()`
      - `td_univariate_statistics()`
      - `td_which_max()`
      - `td_which_min()`
    - TEXT ANALYTIC functions:
      - `td_naivebayes_textclassifier_trainer()`
      - `td_naivebayes_textclassifier_predict()`
      - `td_ngramsplitter()`
      - `td_sentiment_extractor()`
      - `td_text_parser()`
      - `td_word_embeddings()`
    - DATA CLEANING functions:
      - `td_convert_to()`
      - `td_get_futile_columns()`
      - `td_get_rows_without_missing_values()`
      - `td_outlier_filter_fit()`
      - `td_outlier_filter_transform()`
      - `td_pack()`
      - `td_simple_impute_fit()`
      - `td_simple_impute_transform()`
      - `td_string_similarity()`
      - `td_unpack()`
    - HYPOTHESIS TESTING functions:
      - `td_anova()`
      - `td_chi_sq()`
      - `td_ftest()`
      - `td_ztest()`
    - MODEL EVALUATION functions:
      - `td_classification_evaluator()`
      - `td_regression_evaluator()`
      - `td_roc()`
      - `td_silhouette()`
      - `td_train_test_split()`
    - MODEL TRAINING functions:
      - `td_decision_forest()`
      - `td_glm()`
      - `td_glm_per_segment()`
      - `td_kmeans()`
      - `td_knn()`
      - `td_one_class_svm()`
      - `td_svm()`
      - `td_vector_distance()`
      - `td_xg_boost()`
    - FEATURE ENGINEERING UTILITY functions:
      - `td_fill_row_id()`
      - `td_num_apply()`
      - `td_round_columns()`
      - `td_str_apply()`
    - TABLE OPERATOR Functions:
      - `td_read_nos()`
      - `td_write_nos()`
    - BYOM Functions:
      - `td_dataiku_predict()`
      - `td_h2o_predict()`
      - `td_onnx_predict()`
      - `td_pmml_predict()`
      - `td_data_robot_predict()`
  
  - `display_analytic_functions()` - API displays all the available Analytic functions based on Vantage version and 
     categorizes them by function type.

  - Following analytic functions that accept MLE models as input are renamed:
    - `td_decision_forest_predict_sqle()` --> `td_decision_forest_predict_mle_sqle()`
    - `td_decision_tree_predict_sqle()` --> `td_decision_tree_predict_mle_sqle()`
    - `td_glm_predict_sqle()` --> `td_glm_predict_mle_sqle()`
    - `td_naivebayes_textclassifier_predict_sqle()` --> `td_naivebayes_textclassifier_predict_mle_sqle()`
    - `td_naivebayes_predict_sqle()` --> `td_naivebayes_predict_mle_sqle()`
    - `td_svm_sparse_predict_sqle()` --> `td_svm_sparse_predict_mle_sqle()`
    
  - Following functions does not accept models generated by MLE,
    but they now accept the model generated by the Analytics Database Analytic Functions
    exposed by SQLE. 
    - Note - 
        If the Vantage version does not expose the function,
        the below functions won't be available.
      - `td_decision_forest_predict()`
      - `td_glm_predict()`
      - `td_naivebayes_predict()`
      - `td_svm_sparse_predict()`
    
  - The below functions overlap between SQLE and MLE. 
    They will now point to their SQLE equivalent based on the vantage version 
    they are connected to.
    In order to use the corresponding MLE function, we should add the "_mle" suffix.
    - `td_decision_forest()`
    - `td_glm()`
    - `td_histogram()`
    - `td_kmeans()`
    - `td_knn()`
    - `td_text_parser()`
    - `td_naivebayes_textclassifier_predict()`
    - `td_text_parser()`
    - `td_vector_distance()`

#### tdplyr 17.0.0.4
- **Important Notification:**
  - tdplyr is now compatible with `R 4.3.0`.
  - Minimum teradatasql version required is 17.20.0.26 or later.
- Bug Fixes
  - VAL functions now raise appropriate error in case of failures.
    For example, if there is no room in database or insufficient permissions.
  - `cumsum()` and `row_number()` functions work with tdplyr 17.00.00.04.

#### tdplyr 17.0.0.3
- **Important Notification:**
   - tdplyr is now compatible with latest version of dbplyr 2.3.2.
   - Minimum teradatasql version required is 17.20.0.19 or later.
- New Features/Functions
    - `attach_attributes()`: User can now attach attributes to the 'tbl' object using attach_attributes().
      The attributes attached are:
       - databaseName - The name of the database in which the table exists.
       - sourceDefinition - Name of the source of input i.e table name or sql query.
       - sourceType - Type of input source i.e table or query.
       - object - Full name of the table when source type is table, else NULL.
       - baseQuery - Base Query for the tbl.
       - columnDataType - DataTypes of the columns.
       - columnNames - Names of the columns.
- Bug Fixes
  - td_fastload now uploads single column dataframe.


#### tdplyr 17.0.0.2
- Important notification:
  Minimum teradatasql version required is 17.10.0.10 or later.
- New Features/Functions
    - Export data to csv file:
        - `td_to_csv()`
- Updates/Improvements
    - New tdplyr option (`byom.install.location`):
        - Users can specify which database BYOM is intalled in.
        - `td_pmml_predict()` updated to use this option even if user is connected by default to a different database.
- `td_fastexport()`
    - Function enahnced for better performance to export data to CSV file.
    - Arguments `field.separator` and `field.quote.char` can be used to specify the separator and quote character when exporting to CSV file.
- Note: Exporting data to CSV offers better performance than exporting to data.frame, while using `td_fastexport()` and `td_to_csv()`.

#### tdplyr 17.0.0.1
- Important Notification:
  Minimum dbplyr version required is 2.0. tdplyr has been updated to support dbplyr version 2.0 or later.
- New Features/Functions
    - Bring Your Own Models (BYOM): Vignette also available with scoring examples
        - `td_pmml_predict()`
    - Data Export: Added support for FastExport
        - `td_fastexport()`
    - Vantage Analytic Library (VAL) Functions:
        - Association Rules
            - `td_association_valib()`
        - Decision Tree
            - `td_decision_tree_valib()`
            - `td_decision_tree_evaluator_valib()`
            - `td_decision_tree_predict_valib()`
        - Descriptive Statistics
            - `td_adaptive_histogram_valib()`
            - `td_explore_valib()`
            - `td_frequency_valib()`
            - `td_histogram_valib()`
            - `td_overlap_valib()`
            - `td_statistics_valib()`
            - `td_text_analyzer_valib()`
            - `td_values_valib()`
        - Factor Analysis
            - `td_pca_valib()`
            - `td_pca_evaluator_valib()`
            - `td_pca_predict_valib()`
        - Fast KMeans Clustering
            - `td_kmeans_valib()`
            - `td_kmeans_predict_valib()`
        - Linear Regression
            - `td_lin_reg_valib()`
            - `td_lin_reg_evaluator_valib()`
            - `td_lin_reg_predict_valib()`
        - Logistic Regression
            - `td_log_reg_valib()`
            - `td_log_reg_evaluator_valib()`
            - `td_log_reg_predict_valib()`
        - Matrix Building
            - `td_matrix_valib()`
        - Statistical Tests
            - `td_binomial_test_valib()`
            - `td_chi_square_test_valib()`
            - `td_ks_test_valib()`
            - `td_parametric_test_valib()`
            - `td_rank_test_valib()`
        - Reports
            - `td_xml_to_html_report_valib()`
        - Variable Transformation
            - `td_transform_valib()`
            - Transformation Techniques to use with 'Transform'
                - `tdBinning()`
                - `tdDerive()`
                - `tdFillNa()`
                - `tdLabelEncoder()`
                - `tdMinMaxScalar()`
                - `tdOneHotEncoder()`
                - `tdRetain()`
                - `tdSigmoid()`
                - `tdZScore()`
        - Supporting Utilies/Functionality
            - S3 Generic: `print()` - Allows user to print the output of any of the VAL function.
            - View Underlying SQL:
                - `show_query()` - Allows user to print the underlying SQL used 
                  for function execution using the output object.
                - Option `print.val.query` allows user to print the SQL while
                  the VAL function is running. This can be used for debugging 
                  purpose.
    - Sandbox Container Utility Functions
        - `td_cleanup_sandbox_env()`
        - `td_copy_files_from_container()`
        - `td_setup_sandbox_env()`
- Updates/Improvements
    - Newly added tdplyr options:
        - tdplyr has added two new options that provide flexibility to the user
          to control which database must be used to create tables and views,
          generated by the tdplyr APIs, which are garbage collected at the end 
          of the session.
          Following are the two options:
            - `temp.table.database.name` - 
              Specifies the database to create tables into.
            - `temp.view.database.name` - 
              Specifies the database to create views into.
          These options allow user to set the output database without 
          re-creating context.
    - `td_test_script()`
        - Function now also allows testing on local client, i.e., outside of
          sandbox environment, in addition to existing node of sandbox testing.
        - Function `td_setup_test_env()` is deprecated now. Use newly added
          sandbox container utility function `td_setup_sandbox_env()` instead.


#### tdplyr 17.0.0.0
- New Features/Functions
    - Model Cataloging - Functionality to catalog model metadata and related information in the Model Catalog.
        - `td_save_model()` - Save a tdplyr analytic function model.
        - `td_retrieve_model()` - Retrieve a saved model.
        - `td_list_models()` - List accessible models.
        - `td_describe_model()` - List the details of a model.
        - `td_delete_model()` - Remove a model from Model Catalog.
        - `td_publish_model()` - Share a model.
    - Script - An interface to run user scripts in Advanced SQL Engine using Teradata's Script Table Operator (STO).
        - `Script()` - Creates and initializes an object of "ScriptTableOperator" class.
        - The following functions enable the user to run user scripts locally in a containerized enviroment:
            - `td_setup_test_env()` - Setup up the test environment.
            - `td_test_script()` - Test user script in containerized environment.
            - `td_set_data()` - Update/set test data parameters.
        - The following functions enable the user to run user scripts in Advanced SQL Engine:
            - `td_execute_script()` - Execute user script in Vantage.
            - `td_set_data()` - Update/set test data parameters.
    - Vantage File Management Functions
        - `td_install_file()` - Install or replace file in Vantage.
        - `td_remove_file()` - Remove an installed file from Vantage.
    - Time series aggregate functions - Added new SQL translations to support the following time series aggregate functions. Please refer the vignette `time_series_aggregates` for the usage of all time series aggregate functions.
        - `ts.perentile()` - Calculate the nth percentile value of a column.
        - `ts.delta_t()` - Calculate the time difference (i.e, DELTA_T) between starting and ending events.
        - `ts.kurtosis()` - Calculate the kurtosis value of a column.
        - `ts.skew()` - Measure the skewness of the distribution of a column.
        - `ts.sum()` - Calculate the sum of values in the column.
        - `ts.sd()` - Calculate the sample standard deviation of a column.
        - `ts.sdp()` - Calculate the population standard deviation of a column.
        - `ts.var()` - Calculate the sample variance of a column.
        - `ts.varp()` - Calculate the population variance of a column.
        - `ts.min()` - Calculate the minimum value of a column.
        - `ts.max()` - Calculate the maximum value of a column.
        - `ts.mean()` - Calculate the average value of a column.
        - `ts.n()` - Calculate the count of qualified rows in a column.
        - `ts.describe()` - Calculate the statistics of a column.
    - Regular aggregate functions - Added new SQL translations to support the following regular aggregate functions. Please refer the vignette `regular_aggregates` for the usage of all regular aggregate functions.
        - `kurtosis()` - Calculate the kurtosis value of a column.
        - `skew()` - Measure the skewness of the distribution of a column.
        - `n()` - Calculate the count of qualified rows in a column. This dbplyr SQL aggregate function is overwritten to take a column name, with default value as "*" and builds a SQL expression to return count value of type `bit64::integer64`.
        - `n_distinct()` - This SQL aggregate function is updated to return count value of type `bit64::integer64`.
    - Window aggregate functions - Added new SQL translations to support the following window aggregate function. Please refer the vignette `sql-translation` for the usage of all window aggregate functions.
        - `n()` - Calculate the count of qualified rows in a column. This dbplyr SQL aggregate function is overwritten to take a column name, with default value as "*" and builds a SQL expression to return count value of type `bit64::integer64`.
- Updates/Improvements
    - Support added for Stored Password Protection feature. Please refer to the documentation and examples of `td_create_context()` function.
    - Support added in `td_create_context()` to connect to Teradata Vantage using JWT logon mechanism.
    - Using `DBI::dbConnect(tdplyr::NativeDriver(), ...)` creates context unlike earlier releases. To create connection using Teradata SQL Driver for R, please refer the documentation [here](https://github.com/Teradata/r-driver#using-the-teradata-sql-driver-for-r).
    - Updated the way `td_set_context()` works based on the type of the connection object.
    - The `td_nrow()` function returns the count of the rows in tbl_teradata as `bit64::integer64` type.

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
