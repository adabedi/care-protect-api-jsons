POST http://localhost:38381/c19-alpha/0.0.1/cdr/draft

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
    "assessment": {
        "denwis": {
            "q10_other_comment": "comment",
            "q1_breathing": {
                "value": "No change in breathing",
                "code": "at0032"
            },
            "q2_circulation": {
                "value": "Change in circulation",
                "code": "at0036"
            },
            "q3_temperature": {
                "value": "No change in temperature",
                "code": "at0042"
            },
            "q4_mentation": {
                "value": "Change in mentation",
                "code": "at0045"
            },
            "q5_agitation": {
                "value": "Agitation",
                "code": "at0049"
            },
            "q6_pain": {
                "value": "Change in pain",
                "code": "at0052"
            },
            "q7_trajectory": {
                "value": "No change in trajectory",
                "code": "at0054"
            },
            "q8_patient_subjective": {
                "value": "Subjective patient indicator",
                "code": "at0058"
            },
            "q9_nurse_subjective": {
                "value": "Nurse subjective indicator",
                "code": "at0061"
            }
        }
    }
}
```

response body:
```
{
    "situation": null,
    "background": null,
    "denwis": {
        "value": {
            "trend": "decreasing",
            "value": 14
        }
    }
}
```

POST http://localhost:38381/c19-alpha/0.0.1/cdr/

request body:
```
{
    "header": {
        "start_time": "2021-03-11T11:36:06.697Z",
        "uuid": "3B917D6E-30B6-11EB-9B84-84525E058BE1",
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
        "denwis": {
            "q1_breathing": {
                "code": "at0032",
                "value": "No change in breathing",
                "ordinal": 0
            },
            "q2_circulation": {
                "code": "at0036",
                "value": "Change in circulation",
                "ordinal": 1
            },
            "q3_temperature": {
                "code": "at0042",
                "value": "No change in temperature",
                "ordinal": 0
            },
            "q4_mentation": {
                "code": "at0045",
                "value": "Change in mentation",
                "ordinal": 1
            },
            "q5_agitation": {
                "code": "at0049",
                "value": "Agitation",
                "ordinal": 1
            },
            "q6_pain": {
                "code": "at0052",
                "value": "Change in pain",
                "ordinal": 1
            },
            "q7_trajectory": {
                "code": "at0054",
                "value": "No change in trajectory",
                "ordinal": 0
            },
            "q8_patient_subjective": {
                "code": "at0058",
                "value": "Subjective patient indicator",
                "ordinal": 1
            },
            "q9_nurse_subjective": {
                "code": "at0061",
                "value": "Nurse subjective indicator",
                "ordinal": 1
            },
            "q_10_other_comment": "comment",
            "total_score": 14
        }
    }
}
```
response:
200 will be fine too

```
Status Code: 204
```