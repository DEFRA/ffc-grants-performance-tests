# ffc-grants-performance-tests

This repository contains the performance tests for the integrated journey between multiple deployed services that delivers a Grant Application journey.

There is a single test that, for each grant in sequence:

- Runs for 30 seconds
- Ramps up to 50 threads following the full grant journey with a 3 second interval between interactions
- Asserts that all requests receive an HTTP 200 Ok response
- Asserts that the average response time is under 500 ms
- Asserts that no single response is greater that 3000 ms

The intention is to prevent an unexpected performance regression being introduced to the service.

### Running locally

Use JMeter GUI. Set the `Server Name` in `HTTP Request Defaults` to an instance of service `forms-runner-v2`, either hosted or local, and use JMeter to run the test. 

### CDP Portal

Tests are run from the CDP Portal under the `Test Suites` section. Before any changes can be run, a new docker image must be built, this will happen automatically when a pull request is merged into the `main` branch. The reports from the test run are then available through the portal.

## Licence

THIS INFORMATION IS LICENSED UNDER THE CONDITIONS OF THE OPEN GOVERNMENT LICENCE found at:

<http://www.nationalarchives.gov.uk/doc/open-government-licence/version/3>

The following attribution statement MUST be cited in your products and applications when using this information.

> Contains public sector information licensed under the Open Government licence v3

### About the licence

The Open Government Licence (OGL) was developed by the Controller of Her Majesty's Stationery Office (HMSO) to enable
information providers in the public sector to license the use and re-use of their information under a common open
licence.

It is designed to encourage use and re-use of information freely and flexibly, with only a few conditions.
