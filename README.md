[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=com.contrastsecurity.demo%3Aprovider-search&metric=alert_status)](https://sonarcloud.io/summary/new_code?id=com.contrastsecurity.demo%3Aprovider-search)
[![Bugs](https://sonarcloud.io/api/project_badges/measure?project=com.contrastsecurity.demo%3Aprovider-search&metric=bugs)](https://sonarcloud.io/summary/new_code?id=com.contrastsecurity.demo%3Aprovider-search)
[![Code Smells](https://sonarcloud.io/api/project_badges/measure?project=com.contrastsecurity.demo%3Aprovider-search&metric=code_smells)](https://sonarcloud.io/summary/new_code?id=com.contrastsecurity.demo%3Aprovider-search)
[![Coverage](https://sonarcloud.io/api/project_badges/measure?project=com.contrastsecurity.demo%3Aprovider-search&metric=coverage)](https://sonarcloud.io/summary/new_code?id=com.contrastsecurity.demo%3Aprovider-search)
[![Duplicated Lines (%)](https://sonarcloud.io/api/project_badges/measure?project=com.contrastsecurity.demo%3Aprovider-search&metric=duplicated_lines_density)](https://sonarcloud.io/summary/new_code?id=com.contrastsecurity.demo%3Aprovider-search)
[![Lines of Code](https://sonarcloud.io/api/project_badges/measure?project=com.contrastsecurity.demo%3Aprovider-search&metric=ncloc)](https://sonarcloud.io/summary/new_code?id=com.contrastsecurity.demo%3Aprovider-search)
[![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=com.contrastsecurity.demo%3Aprovider-search&metric=reliability_rating)](https://sonarcloud.io/summary/new_code?id=com.contrastsecurity.demo%3Aprovider-search)
[![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=com.contrastsecurity.demo%3Aprovider-search&metric=security_rating)](https://sonarcloud.io/summary/new_code?id=com.contrastsecurity.demo%3Aprovider-search)
[![Technical Debt](https://sonarcloud.io/api/project_badges/measure?project=com.contrastsecurity.demo%3Aprovider-search&metric=sqale_index)](https://sonarcloud.io/summary/new_code?id=com.contrastsecurity.demo%3Aprovider-search)
[![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=com.contrastsecurity.demo%3Aprovider-search&metric=sqale_rating)](https://sonarcloud.io/summary/new_code?id=com.contrastsecurity.demo%3Aprovider-search)
[![Vulnerabilities](https://sonarcloud.io/api/project_badges/measure?project=com.contrastsecurity.demo%3Aprovider-search&metric=vulnerabilities)](https://sonarcloud.io/summary/new_code?id=com.contrastsecurity.demo%3Aprovider-search)

# Vulnerable Spring Boot Application

This application is an intentionally vulnerable Spring Boot application. The intent is to demonstrate the capabilities of Contrast Security's Maven plugin when used with continuous integration (such as TravisCI or CircleCI).

## Build

```
mvn install
```

## Run

```
java -jar target/provider-search-0.0.1-SNAPSHOT.jar
```

* Go to http://localhost:8080/
* Search for zip 21230

## Test

```
mvn clean test
```

## Running With Contrast

You will need an account with Contrast https://www.contrastsecurity.com

* Review the `run-with-contrast` profile settings in `pom.xml`

* Set the following environment variables

```
CONTRAST_MAVEN_USERNAME
CONTRAST_MAVEN_ORGUUID
CONTRAST_MAVEN_TEAMSERVERURL
CONTRAST_MAVEN_APIKEY
CONTRAST_MAVEN_SERVICEKEY
```

* `mvn install -P run-with-contrast`


## Details

The application runs using an in-memory H2 database. Schema and sample data should load on boot.
