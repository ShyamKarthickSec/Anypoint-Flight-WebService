# Flight Information Webservice

This project is a MuleSoft-based webservice designed to manage flight information from three different flight services. It connects to a MySQL database for persistent storage and interacts with both SOAP and REST services to retrieve, update, delete, and add flight data. The webservice ensures robust error handling and seamless integration across various systems.

## Features

- **Retrieve Flight Information:** Fetch flight data from three distinct flight services using both SOAP and REST APIs.
- **Update Flight Information:** Update existing flight records in the MySQL database.
- **Delete Flight Information:** Remove flight records from the MySQL database.
- **Add Flight Information:** Insert new flight records into the MySQL database.
- **Robust Error Handling:** Comprehensive error handling to ensure smooth operation and provide meaningful error messages.

## Technologies Used

- **MuleSoft Anypoint Platform:** The core platform for building the webservice.
- **MySQL Database:** Backend database for storing flight information.
- **SOAP Services:** Used for interacting with some of the flight information services.
- **REST Services:** Used for interacting with other flight information services.

## Prerequisites

- MuleSoft Anypoint Studio
- MySQL Database
- Access credentials for the three flight services (SOAP and REST endpoints)

## Installation

1. **Clone the Repository:**
   ```bash
   git clone [https://github.com/your-repo/flight-info-webservice.git](https://github.com/TheHumanGoogle/Anypoint-Flight-WebService.git)
   ```
2. **Open Anypoint Studio:**
   - Import the cloned project into Anypoint Studio.

3. **Configure Database Connection:**
   - Open `src/main/resources/configuration-properties.yaml` and update the MySQL connection details.
   ```yaml
   db.url=jdbc:mysql://localhost:3306/your-database
   db.username=your-username
   db.password=your-password
   ```

4. **Run the Application:**
   - Right-click the project in Anypoint Studio and select `Run As` > `Mule Application`.

## Usage

- **Retrieve Flight Information:**
  - Endpoint: `/api/flights`
  - Method: `GET`
  - Description: Fetches flight information from the connected flight services and stores it in the MySQL database.

- **Update Flight Information:**
  - Endpoint: `/api/flights/{id}`
  - Method: `PUT`
  - Description: Updates the flight information for the given flight ID.
  - Payload:
    ```json
    {
      "flightNumber": "ABC123",
      "departureTime": "2024-07-15T10:00:00Z",
      "arrivalTime": "2024-07-15T14:00:00Z",
      "status": "On Time"
    }
    ```

- **Delete Flight Information:**
  - Endpoint: `/api/flights/{id}`
  - Method: `DELETE`
  - Description: Deletes the flight information for the given flight ID.

- **Add Flight Information:**
  - Endpoint: `/api/flights`
  - Method: `POST`
  - Description: Adds new flight information.
  - Payload:
    ```json
    {
      "flightNumber": "DEF456",
      "departureTime": "2024-07-16T08:00:00Z",
      "arrivalTime": "2024-07-16T12:00:00Z",
      "status": "Scheduled"
    }
    ```

## Error Handling

The webservice includes robust error handling mechanisms to manage different types of errors, such as:

- **Database Connection Errors:** Handles scenarios where the MySQL database is unreachable.
- **External Service Errors:** Manages errors from the SOAP and REST flight services, including timeout and invalid responses.
- **Validation Errors:** Ensures that incoming requests contain valid data and provides meaningful error messages for invalid inputs.

## Contributing

We welcome contributions to improve this webservice. Please follow these steps to contribute:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes and commit them (`git commit -m 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a Pull Request.

## Disclaimer
This Project was done as part of DEX401 Course and this was done by me as a practice for MCD Level-1 Exam.

---

Feel free to reach out if you have any questions or need further assistance with setting up or using this webservice. Happy coding!
