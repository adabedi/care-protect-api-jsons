POST http://localhost:38381/c19-alpha/0.0.1/cdr/draft
With SEPSIS there is still not decided how middleware wants to handle a sepsis object (clinical/no_clinical)
request body, current one:
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
        "sepsis": {
            "risk_factors_for_sepsis": [
                {
                    "value": "Age over 75",
                    "code": "at0002"
                }
            ],
            "likely_source_of_infection": [
                {
                    "value": "Urine",
                    "code": "at0004"
                },
                {
                    "value": "Brain",
                    "code": "at0003"
                }
            ],
            "red_flags": [
                {
                    "value": "Unable to catch breath / barely able to speak",
                    "code": "at0014"
                },
                {
                    "value": "Unable to stand / collapsed",
                    "code": "at0013"
                }
            ],
            "amber_flags": [
                {
                    "value": "Signs of wound infection",
                    "code": "at0018"
                }
            ],
            "999_flags": [
                {
                    "value": "‘I feel I might die’",
                    "code": "at0006"
                },
                {
                    "value": "Skin mottled, ashen, blue or very pale",
                    "code": "at0007"
                }
            ]
        }
    }
}
```



response body:
```
{
situation: null,
background: null
 sepsis: {
      value: {
        value: 'amber',
      },
    },
}
```

POST http://localhost:38381/c19-alpha/0.0.1/cdr/draft

request body:
```
{
    "header": {
        "start_time": "2021-03-11T11:49:16.465Z",
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
        "sepsis_screening": {
            "sepsis_clinical_screening_age_12_plus": { //or sepsis_no_clinical_screening_age_12_plus
                "risk_factors_for_sepsis": [ //optional
                    {
                        "value": "Impaired immunity (e.g diabetes, steroids, chemotherapy)",
                        "code": "at0003"
                    },
                    {
                        "value": "Age over 75",
                        "code": "at0002"
                    }
                ],
                "likely_source_of_infection": [ // optional
                    {
                        "value": "Brain",
                        "code": "at0003"
                    },
                    {
                        "value": "Abdominal pain / distension",
                        "code": "at0009"
                    }
                ],
                "red_flags": [ // optional
                    {
                        "value": "Skin that is very pale, mottled , ashen or blue",
                        "code": "at0016"
                    }
                ],
                "amber_flags": [ // optional
                    {
                        "value": "Behavioural change / reduced activity",
                        "code": "at0013"
                    },
                    {
                        "value": "Signs of wound infection",
                        "code": "at0018"
                    }
                ],
                "999_flags": [ // optional
                    {
                        "value": "Skin mottled, ashen, blue or very pale",
                        "code": "at0007"
                    },
                    {
                        "value": "Extreme shivering or muscle pain",
                        "code": "at0003"
                    }
                ]
            }
        }
    }
}
```

response:
200 will be fine too


```
Status Code: 204
```

Requested by Ian as an correct, still need to be done decison how Middleware prefer handle that.:
```
 "assessment": {
        "sepsis": {
"sepsis_screening":
                    {
                        "sepsis_clinical_screening_age_12_plus":
                            {
                                // risk_factors
                                //at0002 Age over 75
                                //at0003 Impaired immunity (e.g diabetes, steroids, chemotherapy)
                                //at0004 Recent trauma / surgery / invasive procedure
                                //at0005 Indwelling lines / IVDU / broken skin
                                "risk_factors": [
                                    {
                                        "code": "at0002",
                                        "value": "Age over 75"
                                    },
                                    {
                                        "code": "at0004",
                                        "value": "Recent trauma / surgery / invasive procedure"
                                    }
                               ],
                                "likely_source_of_infection": [
                                    {
                                        "code": "at0002",
                                        "value": "Respiratory"
                                    }
                                ],
                                "red_flags": [
                                    {
                                        "code": "at0005",
                                        "value": "Heart rate ≥ 130 per minute"
                                    }
                                ],
                                "amber_flags": [
                                   {
                                    "code": "at0005",
                                     "value": "Immunosuppressed"
                                    }
                                ],
                                "a999_flag": [
                                    {
                                        "code": "at0006",
                                        "value": "‘I feel I might die’"
                                    }
                                ]
                            }
                        ,
                        "sepsis_non_clinical_screening_age_12_plus":
                            {
                                // Risk factors
                                //at0002 Age over 75
                                //at0003 Impaired immunity (e.g diabetes, steroids, chemotherapy)
                                //at0004 Recent trauma / surgery / invasive procedure
                                //at0005 Indwelling lines / IVDU / broken skin
                                "risk_factors": [
                                    {
                                        "code": "at0002",
                                        "value": "text"
                                    }
                               ],
                                "likely_source_of_infection": [
                                    {
                                        "code": "at0004",
                                        "value": "text"
                                    }
                                ],
                                "red_flags": [
                                    {
                                        "code": "at0012",
                                        "value": "Objective evidence of new or altered mental state"
                                    }
                                ],
                                "amber_flags": [
                                   {
                                    "code": "at00013",
                                     "value": "Behavioural change / reduced activity"
                                    }
                                ],
                                "a999_flag": [
                                    {
                                        "code": "at0004",
                                        "value": "text"
                                    }
                                ]
                            },}}
```