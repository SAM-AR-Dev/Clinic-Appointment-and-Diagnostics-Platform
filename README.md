# Clinic-Appointment-and-Diagnostics-Platform - ER Diagram

https://app.eraser.io/workspace/YUGg5YO0SW39S0ykIhSd?origin=share

***

This README outlines the database schema designed for a comprehensive, modern clinic management system. The design handles everything from basic patient scheduling to advanced features like pharmacy prescriptions, lab diagnostics, and insurance-based billing.

## Tool Used
This schema was built using **Eraser.io** diagram-as-code syntax. You can copy the code block into an Eraser workspace to instantly generate a clean, relational visual diagram.

## System Architecture

The database is divided into six core operational modules:

### 1. Facility & Staffing
* **`departments`**: Physical or organizational sectors of the clinic (e.g., General Medicine, Radiology).
* **`specialties`**: Specific medical focuses linked to departments.
* **`doctors`**: Medical professionals linked to their respective specialties.
* **`lab_technicians`**: Staff members responsible for collecting diagnostic samples.
* **`rooms`**: Physical spaces where appointments take place.

### 2. Patient Records
* **`patients`**: Core demographic and contact information.
* **`medical_history`**: Separated from the main profile to track chronic conditions, allergies, and past surgeries over time.

### 3. Scheduling & Visits
* **`appointments`**: Handles the scheduling, time slots, and room assignments.
* **`consultations`**: Created only when an appointment actually takes place. Stores doctor's notes, symptoms, and diagnoses.

### 4. Pharmacy Module
* **`medications`**: A master catalog of drugs available or prescribable by the clinic.
* **`prescriptions`**: Links a specific consultation to a medication, detailing the dosage, frequency, and duration.

### 5. Diagnostics & Labs
* **`tests`**: The master catalog of lab tests and imaging services with base prices.
* **`prescribed_tests`**: Links a consultation to a required test, tracking which lab technician handled the sample collection.
* **`reports`**: The final medical results linked directly to the prescribed test.

### 6. Insurance & Billing
* **`insurance_providers`**: Master list of accepted insurance companies.
* **`patient_insurance`**: Links a patient to their specific policy number and coverage limits.
* **`invoices`**: The total master bill generated for a specific appointment/visit.
* **`payments`**: Records of individual transactions applied against an invoice, allowing for partial payments or multiple payment methods.
