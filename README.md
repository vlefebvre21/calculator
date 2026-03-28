# Calculator.js: Node.js REST API Calculator

## Description

This is a demonstration Node.js project that implements a simple pocket calculator via REST APIs. It supports basic arithmetic operations (addition, subtraction, multiplication, division) on integers. The app is built with Express.js and includes a comprehensive test suite using Mocha and Chai for unit testing. XML output is supported via `mocha-junit-reporters` for integration with CI/CD tools like Azure DevOps.

### Features
- **RESTful Endpoints**: Perform calculations via HTTP POST requests to `/add`, `/subtract`, `/multiply`, `/divide`.
- **Error Handling**: Validates inputs and returns appropriate HTTP status codes (e.g., 400 for invalid ops).
- **Testing**: Full unit test coverage with Mocha/Chai; run `npm test` to execute.
- **CI/CD Ready**: JUnit XML reports for tools like Azure DevOps, Jenkins, etc.
- **Extensible**: Easy to add more operations or integrate with frontend UIs.

### Architecture Overview
- **Server**: Express.js app listening on port 3000.
- **Routes**: Arithmetic operations mapped to controller functions.
- **Tests**: Located in `/test/`, using supertest for API mocking.
- **Dependencies**: Node.js >= 14, npm packages: express, mocha, chai, supertest, mocha-junit-reporter.

Key design choice: Stateless API design for scalability; no sessions or databases needed for core functionality.

### Installation
1. Clone the repository:
   ```
   git clone https://github.com/vlefebvre21/calculator.git
   cd calculator
   ```
2. Install dependencies:
   ```
   npm install
   ```
3. Start the server:
   ```
   npm start  # or node server.js
   ```

### Usage
The API is accessible at `http://localhost:3000`.

#### Example Requests (using curl)
- Addition: `curl -X POST http://localhost:3000/add -H "Content-Type: application/json" -d '{"a": 5, "b": 3}'`
  - Response: `{"result": 8}`
- Subtraction: `curl -X POST http://localhost:3000/subtract -H "Content-Type: application/json" -d '{"a": 10, "b": 4}'`
  - Response: `{"result": 6}`
- Multiplication: `curl -X POST http://localhost:3000/multiply -H "Content-Type: application/json" -d '{"a": 7, "b": 2}'`
  - Response: `{"result": 14}`
- Division: `curl -X POST http://localhost:3000/divide -H "Content-Type: application/json" -d '{"a": 15, "b": 3}'`
  - Response: `{"result": 5}` (Note: Division by zero returns 400 error)

#### Testing
Run the test suite:
```
npm test
```
This executes Mocha tests and generates JUnit XML output in `/test-results.xml` for CI integration.

### Contributing
- Fork the repo and create a feature branch.
- Add tests for new features.
- Ensure code coverage remains high.
- Submit a Pull Request.

### License
MIT License. See LICENSE file for details.

For questions or issues, open a GitHub issue.

