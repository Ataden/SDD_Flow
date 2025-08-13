<TESTING_TOOLS>
Your testing tools are:
- `jest` for unit and integration testing in `frontend/` 
- `pytest` for unit and integration testing in `backend/`
- `playwright` for end-to-end testing - installed in the `frontend` folder, place test files in the `frontend/e2e` folder
</TESTING_TOOLS>

<TESTING_COMMANDS>
1. For unit and integration tests in backend:

Activate the virtual environment and run all tests:
`cd backend && source venv/bin/activate && pytest` for backend unit and integration tests 

Run only unit tests:
`cd backend && source venv/bin/activate && pytest tests/unit/`

Run only integration tests:
`cd backend && source venv/bin/activate && pytest tests/integration/`

2. For frontend unit and integration tests (jest):
`cd frontend && npm test` for frontend integration tests

3. For end-to-end tests (playwright):
Use Playwright MCP to run end-to-end tests

</TESTING_COMMANDS>

<TEST_NAMING_CONVENTIONS>
Name all tests and files according to the following rules:

**Unit tests:**
In tests/unit folder.
Start names with prefix "UT-".
Add the id and the name of the component being tested (according to the TDDoc in 'docs/5.3_tech_design.md') and then testId - a unique number of the test for this service (replace dot with underscore for file names!!!). When adding a new test, always check for existing tests and increment <testID> to ensure it is unique. Then add the name of the test.

When you create a test for an internal component not listed in the TDDoc (e.g. a React hook or a python class), add its name to the test name and the file name.
Example: 
- `UT_B1.CallService_01 Create call with valid data` - unit test for creating call with valid data. Must be placed in `tests/unit/UT_B1_CallService.py` file (note the dot between the test name and the test ID is replaced with underscore for file names!!!) among other unit tests of the Call Service.
- `UT_F1.7_CalendarView_useCalendar_01 Calendar hook initialization with authentication` - unit test for calendar hook initialization with authentication. Must be placed in `tests/unit/UT_F1_7_CalendarView_useCalendar.tsx` file (note the dot between the test name and the test ID is replaced with underscore for file names!!!) among other unit tests of the useCalendar hook.

Group all unit tests of the same component in one file file.

**API and integration tests:**
In tests/integration folder.
Start names with prefix "API-" or "INT-".
Add the id and name of the initiatinng component and the interaction ID being tested (according to the TDDoc in 'docs/5.3_tech_design.md')

Example: 
- `API_F1.AuthLoginForm_I1 Submit login form with valid data` - API integration test for submitting login form with valid data - interaction `I1`,  Must be placed in `tests/integration/API_F1_AuthLoginForm_I1.py` file (note the replacement of the dot with underscore for file name!!!) - one file per interaction being tested.
- `INT_B2.CallService_I2 Create call with valid data` - integration test for creating call in DB - interaction `I2`, Must be placed in `tests/integration/INT_B2_CallService_I2.py` file - one file per interaction being tested. In one file all tests for this interaction must be placed.

Group all integration tests of the same interaction in one file.

**End-to-end tests:**
In tests/e2e folder.
Start names with prefix "E2E-".
Add the id of the initiatinng frontend component (according to the TDDoc in 'docs/5.3_tech_design.md')
Create e2e tests ONLY if a frontend component is affected, otherwise skip e2e tests.

Example: 
- `E2E_F5.Chat Download  messages history in chat` - end-to-end test for downloading messages history in chat,  Must be placed in `frontend/e2e/E2E_F5_Chat.py` file (note the replacement of the dot with underscore for file name!!!). All e2e tests for user interaction with this F5.Chat component must be placed in this file.

No need to prepend "test_" for `pytest` tests - pitest.ini file allows to discover tests without it.

</TEST_NAMING_CONVENTIONS>

<TEMPORARY_DATA_LOCATION>
When you create test data or temporary scripts, it should be placed in the `test/tmp` folder.
Crucual!!! You also have to add to the test the deletion of the test data from existing DB after the test is completed, if it is not deleted during the test scenario
</TEMPORARY_DATA_LOCATION>

<DATABASE_IN_INTEGRATION_TESTS>
For integration tests:
- Do NOT mock the database connection or ORM session. Avoid using mock libraries for any database interactions.
- Use a real temporary database, such as SQLite in tests/tmp folder.
- Apply the real database migrations (via Alembic) to prepare the schema before running any tests.
- Use FastAPI's dependency override to inject the test database session in place of the production database.
- Ensure test isolation by rolling back transactions, or resetting the schema/data after each test case or test module.
- After the tests, ensure the test database is fully torn down or cleaned up.

The goal is to verify actual integration between FastAPI, the ORM, and the database schema using real queries.
</DATABASE_IN_INTEGRATION_TESTS>

<E2E_TEST_AUTHENTICATION>
For E2E tests authentication for the interface behind the login page is performed using the following test credentials:

Email: test@example.com
Password: password123

</E2E_TEST_AUTHENTICATION>

<BACKEND_LOGS>
Backend logs are available by http://localhost:8000/logs/?n=10 (last 10 lines, adjust if needed)
ALWAYS check the logs for any errors or warnings during the tests
</BACKEND_LOGS>

<E2E_PLAYWRIGHT>
When you fill in the forms, always do it in one command `await page.fill()`, for all fields in the form not one command for each field

I REPEAT: Use Playwright MCP to run end-to-end tests. IT IS CRUCIAL!!!
</E2E_PLAYWRIGHT>
