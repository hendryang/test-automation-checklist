# Test Automation Checklist [Growing]

## Purpose
To streamline and standardized good practice of testing automation for both Framework and Project level.

Refer to : https://github.com/hendryang/rapid-automation for sample framework/project compliance to this checklist.

## Checklist

| Test Automation Checklist    |                                                                 | Test |
| ---------------------------- | -------------------------------------------------------------------------- | ---- |
| Configuration and Management | Configuration injection                                                    | All configuration related to browser should be separated out from the test script. |
|                              | Secure test credentials                                                    | All credentials related information should not be part of test script or repository, it should be injected. |
|                              | Data-driven test data (JSON/XLSX)                                          | All test related data should be separated out from the test script, it should be stored as external file/config |
| Test Development             | Primitive abstraction                                                      | All user action against single web element which require "wait time" should be packaged as library |
|                              | Component-level abstraction                                                | All test against a component (eq. Grid/Table, dropdown, slider, radiobutton) should be packaged as reusable library |
|                              | Page object design pattern                                                 | Utilizing page object pattern to manage the test |
|                              | Reduce usage of explicit wait in test code                                 | Repetitive and excessive usage of explicit wait should be packaged as library (see Primitive abstraction) |
|                              | Justifiable usage of sleep or wait                                         | Discourage to use hard sleep/wait, it should be handled with explicit wait whenever possible |
|                              | Logging capability rather than standard output                             | Logging to both file and console rather than using StdOut (eq. console.log or System.out.println ) |
|                              | Support browser-based assertion                                            | Support assertion of  state or property of webelement |
|                              | Support general assertion                                                  | Support general assertion such as – 1 is greater than 2 , Array A contains a |
|                              | Utilizing Hook for setup and teardown                                      |  |
| Test Execution               | Parallel Execution                                                         | Ability to execute test in parallel both locally and jenkins |
|                              | Serial Execution                                                           | Ability to force test to only run one test at a time for debugging purpose |
|                              | Hybrid Execution (serial+parallel)                                         | Ability to combine both parallel and serial execution – eq. some test unable to run in parallel due to dependencies, we can temporarily run them in serial while others are using parallel. |
|                              | Support Headless execution                                                 |  |
|                              | Test execution in docker                                                   |  |
|                              | Group execution (by Tag, file, folder,etc)                                 | Ability to run certain test based its tag, filename or folder |
|                              | Test profile to support multi-environment test                             | Ability to run test on different environment/setting in runtime |
| Test Reporting               | Screenshot on failure                                                      |  |
|                              | Video recording on failure                                                 |  |
|                              | Support JSON report                                                        | Not required, however JSON is recommended for integration with other tool |
|                              | Integrate with reporting framework (allure/cucumber)                       | Primarily for Jenkins |
| Test Documentation           | All public method should be documented when necessary (eq. Javadoc, jsdoc) | Primarily for method that is being use repetitively or complicated |
|                              | README page should be setup                                                | Project README page should be setup with minimum details of test setup/execution/reporting and jenkins setup|
| CI/CD                        | Use dependency management (eq. Maven, NPM, Yarn)                           |  |
|                              | Jenkins execution and reporting                                            |  |


## Maintainer
- hendryang91@gmail.com