# Doctor Finder
Doctor Finder is a minimal search engine to find Doctors using [BetterDoctor API](https://developer.betterdoctor.com/)

## Task
* Implement doctor search by name which calls BetterDoctor API. (Doctor Search `GET /doctors`)
* Show list of doctors with names and their titles.
* Upon clicking the link for Doctor, show following data for the Doctor:
  * Doctor's name (String): Concatenation of first name, middle name, and last name
  * Doctor's title (String)
  * Doctor's specialties (Array)
  * Doctor's insurances (Array): Map "insurance_uids" to the labels. (Retrieve insurance providers and plans `GET /insurances`)
  * Is Doctor a Primary Care Physician? (Boolean) 
    * If Doctor's specialties comes within the following list then doctor is a Primary Care Physician:
      ```
        'family-practitioner', 'family-medicine-adult-medicine',
        'general-practice', 'general-practitioner', 'internist',
        'geriatric-medicine-doctor', 'internal-medicine-adolescent-medicine',
        'adolescent-medicine-pediatrician', 'obstetrics-gynecologist',
        'general-practitioner', 'pediatrician', 'primary-care-nurse-practitioner',
        'family-nurse-practitioner', 'nurse-practitioner', 'adolescent-medicine-pediatrician',
        'family-medicine-geriatric-medicine', 'physician-assistant',
        'medical-physician-assistant', 'adult-medicine-physician-assistant'
      ```
  * JSON response should look like this: 
    ```json
    [
      {
        "name": "Neel R Anand",
        "title": "MD",
        "insurances": [
          "Better Insurance HMO",
          "Better Insurance PPO"
        ],
        "specialties": [
          "psychiatrist"
        ],
        "primary_care_physician": false
      },
      {
        "name": "John Doe",
        "title": "MD",
        "insurances": [
          "Better Network PPO",
          "Best HMO"
        ],
        "specialties": [
          "general-practitioner"
        ],
        "primary_care_physician": true
      }
    ]
    ```
* Feel free to show the data however you like on the view.

* BONUS Points:
  * Multi-field search by specialty, location or any keyword.
  * Use minimal requests to fetch the data from the BetterDoctor API.  

## Instructions
* Clone this repo
* Create secret_key for your app: `bundle exec rake secret` (Check secrets.yml on this project)
* Get an API key from [BetterDoctor API](https://developer.betterdoctor.com/)
* Paste the API key in .env file

Reference: [BetterDoctor API documentation](https://developer.betterdoctor.com/documentation15#/)

Note: Please do not post the solution as this is a public repo.
