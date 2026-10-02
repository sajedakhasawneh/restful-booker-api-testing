#Restful-Booker API Testing 

##Project Overview
This repository contains a complete **API Testing Suite** for the [Restful-Booker](https://restful-booker.herokuapp.com/) platform using **Postman**. The project focuses on validating CRUD operations, testing edge cases, managing dynamic authentication, and implementing non-functional SLA checks.

## Tools & Technologies Used
- **API Testing:** Postman
- **Scripting Language:** JavaScript (Postman Sandbox)
- **Environment Management:** Postman Environment Variables (`base_url`, `token`)
- **Documentation:** Markdown, GitHub

## Key Technical Implementation
1. **Dynamic Authentication:** Automated token generation via `POST /auth` using JavaScript scripts to capture and inject the `token` dynamically into protected endpoints (`PUT`, `PATCH`, and `DELETE`).
2. **Collection-Level Assertions:** Automated test scripts verifying HTTP status codes (`200 OK`, `201 Created`) and performance response times (`< 2000ms`).
3. **End-to-End Validation:** Full lifecycle testing for booking creation, retrieval, updates, and deletion.

##  Defect Discovery & Root Cause Analysis
During manual and automated testing, several defects were identified and documented:
- **BUG-01 (Backend Logic):** `GET /booking` with combined parameters (`firstname` and `lastname`) returns `200 OK` with an empty array `[]`, despite records existing. *(Failed SQL AND logic).*
- **BUG-02 (Case Sensitivity):** Filtering is strictly case-sensitive (`Mary` returns results, while `mary` returns empty).


##  How to Run This Collection
1. Clone this repository or download the JSON files.
2. Open Postman and click **Import**.
3. Select both `Restful-Booker.postman_collection.json` and `Restful-Booker-Env.postman_environment.json`.
4. Set the active environment to **Restful-Booker-Env**.
5. Open **Collection Runner** and run the entire collection.
