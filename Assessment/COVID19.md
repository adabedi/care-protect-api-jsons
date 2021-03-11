POST http://localhost:38381/c19-alpha/0.0.1/cdr/draft
Probably draft will be not needed. 
?????????
Needs updates, not confirmed.!

POST http://localhost:38381/c19-alpha/0.0.1/cdr

request body:
```
{
    "header": {
        "start_time": "2021-02-10T13:34:58.446Z",
        "uuid": "0F878EC8-FECE-42DE-AE4E-F76BEFB902C2",
        "healthcare_facility": "Glen Carse Care Home",
        "composer": {
            "name": "RN Joyce Brown",
            "id": {
                "type": "NMC",
                "id": "12342341",
                "namespace": "uk.org.nmc"
            }
        }
    },
       "situation": {
        "soft_signs": [
            "Withdrawn"
        ]
    },
    "background": {
        "frailty": [
            {
                "code": "at0012",
                "value": "Very Severely Frail"
            }
        ],
        "height": {
            "magnitude": 165,
            "unit": "cm"
        },
        "weight": {
            "magnitude": 50,
            "unit": "kg"
        }
    },
    "assessment": {
       "covid": {
        "first_symptoms_date":"2021-03-27", //if we have symptoms then date is mandatory
        "covid_notes":"note", //optional
        "symptoms":[
           {
              "value":"Shortness of breath",
              "code":"267036007",
              "terminology":"SNOMED-CT"
           },
           {
              "value":"Nausea and vomiting",
              "code":"16932000",
              "terminology":"SNOMED-CT"
           }
        ],
        // "contact":[] symptomps or contact is mandator 
     }
    }
}
```

response body:
200 will be fine too
```
Status Code: 204
```