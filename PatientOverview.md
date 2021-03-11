GET http://localhost:38381/c19-alpha/0.0.1/meta/demographics/patient_list?search_key=id&search_value=0F878EC8-FECE-42DE-AE4E-F76BEFB902C2

response body:
```
{
    assessment: {
      news2: {
        value: {
          trend: 'same',
          value: 4,
          clinicalRisk: 'at0057',
        },
      },
      covid: {
        value: null,
      },
      sepsis: {
        value: {
          value: 'amber',
        },
      },
      denwis: {
        value: {
          trend: 'decreasing',
          value: 14,
        },
      },
    },
    birthDateAsString: '1965-12-13',
    gender: 'female',
    name: 'Mrs Fredrica Smith',
    location: 'Bedroom',
    birthDate: -127872000,
    nhsnumber: '3333333333',
    id: '3B9170C6-30B6-11EB-9B84-84525E058BE1',
  }
```