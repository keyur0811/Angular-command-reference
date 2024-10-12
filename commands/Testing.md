# Testing

This document outlines the commands used for testing Angular applications, including unit tests and end-to-end (E2E) tests.

## Unit Testing

### Run Unit Tests
To execute the unit tests in your application using Karma, use the following command:

```bash
ng test
```
- This command will launch the Karma test runner and watch for file changes.
- By default, it will open a browser window to display the test results.
- You can also run tests without opening the browser by adding the `--no-watch` flag:
  
```bash
ng test --no-watch
```

### Run Tests with Coverage
To generate a code coverage report along with running the unit tests, use:

```bash
ng test --code-coverage
```
- The coverage report will be generated in the `coverage` directory.
- You can view the coverage results in your browser by opening the `index.html` file in the `coverage` directory.

### Running Tests in Watch Mode
To continuously run tests while you develop and automatically re-run them on file changes:

```bash
ng test --watch
```
- This mode will keep the test runner running in the background.

## End-to-End (E2E) Testing

### Run End-to-End Tests
To execute E2E tests using Protractor, use the following command:

```bash
ng e2e
```
- This command will compile the application and run the E2E tests defined in the `e2e` folder.
- Ensure you have the Protractor configuration set up correctly in the `e2e/protractor.conf.js` file.

### Run E2E Tests with a Specific Browser
To run the E2E tests in a specific browser, you can add the `--browser` option:

```bash
ng e2e --browser=chrome
```
- You can replace `chrome` with other supported browsers like `firefox` or `safari`.

### Run E2E Tests with Specific Configuration
You can specify a configuration file when running E2E tests:

```bash
ng e2e --configuration=production
```
- This allows you to run tests against a specific environment configuration.

### Generate E2E Test Reports
To generate reports for your E2E tests, configure the Protractor settings in the `e2e/protractor.conf.js` file. You can use reporters like `jasmine-reporters` or `mocha`.

## Summary

Use these commands to effectively run and manage your unit and end-to-end tests in Angular. Testing is crucial for ensuring the reliability and quality of your application, so familiarize yourself with these commands and integrate them into your development workflow.
