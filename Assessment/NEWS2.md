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
        "news2": {
            "respiration_rate": {
                "magnitude": "55",
                "units": "/min"
            },
            "spo2": "55",
            "systolic": {
                "magnitude": "55",
                "units": "/mmHg"
            },
            "diastolic": {
                "magnitude": "44",
                "units": "/mmHg"
            },
            "pulse": {
                "magnitude": "34",
                "units": "/min"
            },
            "acvpu": {
                "value": "Voice"
            },
            "temperature": {
                "magnitude": "34",
                "units": "℃"
            },
            "inspired_oxygen": {
                "method_of_oxygen_delivery": "Room Air"
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
    "news2": {
        "clinicalRisk": {
            "localizedLabels": {
                "en": "Low"
            },
            "value": "at0057",
            "localizedDescriptions": {
                "en": "Ward-based response."
            },
            "label": "Low"
        },
        "trend": "same",
        "score": {
            "consciousness": {
                "value": "CVPU",
                "code": "at0025",
                "ordinal": 3
            },
            "systolic_blood_pressure": {
                "code": "at0017",
                "ordinal": 3,
                "value": "≤90"
            },
            "total_score": 18,
            "pulse": {
                "ordinal": 3,
                "code": "at0010",
                "value": "≤40"
            },
            "air_or_oxygen": {
                "value": "Air",
                "code": "at0036",
                "ordinal": 0
            },
            "respiration_rate": {
                "code": "at0064",
                "ordinal": 3,
                "value": "≥25"
            },
            "temperature": {
                "ordinal": 3,
                "code": "at0039",
                "value": "≤35.0"
            },
            "spo_scale_1": {
                "value": "≤91",
                "ordinal": 3,
                "code": "at0033"
            }
        }
    }
}
```

POST http://localhost:38381/c19-alpha/0.0.1/cdr
request body:
```
{
    "header": {
        "start_time": "2021-03-11T11:22:32.353Z",
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
            "Increased anxiety/agitation"
        ]
    },
    "background": {
        "frailty": [
            {
                "code": "at0011",
                "value": "Severely Frail"
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
        "news2": {
            "spo2": 55,
            "systolic": {
                "magnitude": 55
            },
            "diastolic": {
                "magnitude": 44
            },
            "pulse": {
                "magnitude": 34
            },
            "acvpu": {
                "code": "at0006",
                "value": "Voice"
            },
            "temperature": {
                "magnitude": 34
            },
            "inspired_oxygen": {
                "method_of_oxygen_delivery": "Room Air"
            },
            "respirations": {
                "magnitude": 55
            },
            "news2_score": {
                "consciousness": {
                    "value": "CVPU",
                    "code": "at0025",
                    "ordinal": 3
                },
                "systolic_blood_pressure": {
                    "code": "at0017",
                    "ordinal": 3,
                    "value": "≤90"
                },
                "total_score": 18,
                "pulse": {
                    "ordinal": 3,
                    "code": "at0010",
                    "value": "≤40"
                },
                "air_or_oxygen": {
                    "value": "Air",
                    "code": "at0036",
                    "ordinal": 0
                },
                "respiration_rate": {
                    "code": "at0064",
                    "ordinal": 3,
                    "value": "≥25"
                },
                "temperature": {
                    "ordinal": 3,
                    "code": "at0039",
                    "value": "≤35.0"
                },
                "spo_scale_1": {
                    "value": "≤91",
                    "ordinal": 3,
                    "code": "at0033"
                },
                "clinical_risk_category": {
                    "value": "Low",
                    "terminology": "local",
                    "code": "at0057"
                }
            }
        }
    }
}:
```
response:
200 will be fine too

```
Status Code: 204
```