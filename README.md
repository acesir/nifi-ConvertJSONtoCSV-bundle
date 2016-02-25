NiFi ConvertJSONtoCSV
==========

Convert multi nested JSON files into denormalized, flattened out version of the CSV.

example of JSON
```json
[
    {
        "title": "Professional JavaScript",
        "authors": [
            "Nicholas C. Zakas"
        ],
        edition: 3,
        year: 2011
    },
    {
        "title": "Professional JavaScript",
        "authors": [
            "Nicholas C.Zakas"
        ],
        edition: 2,
        year: 2009
    },
    {
        "title": "Professional Ajax",
        "authors": [
            "Nicholas C. Zakas",
            "Jeremy McPeak",
            "Joe Fawcett"
        ],
        edition: 2,
        year: 2008
    }
]
```
Output produced by the processor would be:
```csv
year,edition,title,authors[1],authors[2],authors[3]
2011,3,Professional JavaScript,Nicholas C. Zakas,,
2009,2,Professional JavaScript,Nicholas C.Zakas,,
2008,2,Professional Ajax,Nicholas C. Zakas,Jeremy McPeak,Joe Fawcett
