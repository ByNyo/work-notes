## **Unit Testing**
Unit tests are often isolated because they only test single functions or methods. The main goal is to make sure that every part of the software works as intended.
##### Tools (Go)
testing-Packet

## Integration Testing
Integration tests concentrate on Interactions between modules or services (e.g. API) inside an application. The goal is to make sure that the components work togehter as intended.
##### Tools (Go)
testing-Packed combined with http/test

## E2E Testing
End-to-end tests are testing the whole workflow of an application, from Front-End to Back-End.
##### Tools (Go)
Cypress & Selenium

## Differences

| Feature             | Unit Testing                               | Integration Testing                            | End-to-End Testing                 |
| ------------------- | ------------------------------------------ | ---------------------------------------------- | ---------------------------------- |
| Focus /<br>Use case | Individual units / <br>function / features | Interactions between <br>modules               | Complete application <br>workflows |
| Isolation           | Isolated from other <br>modules / features | Tests components <br>together                  | Tests the entire system            |
| Speed               | Fast                                       | Moderate                                       | Slow                               |
| Complexity          | Simple                                     | Moderate complexity                            | High complexity                    |
| Tools               | **testing**, JUnit, Jest                   | Combination of unit tools,<br>HTTP mocks, etc. | Selenium, Cypress                  |