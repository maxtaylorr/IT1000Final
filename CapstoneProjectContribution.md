# Capstone Project

For my final capstone project myself and a team of 3 others created a social night life bar app

The most significant portion I helped with was data structures

**JSON Data**

`{
  "date": "03/12/2019",
  "type": "barInfo",
  "status": "ok",
  "bars": [
    {
      "id": "1",
      "name": "Harpos",
      "latitude": "38.9506° N",
      "longitude": "92.3268° W",
      "hours": "11:00 A.M. to 1 A.M.",
      "deals": [
        {
          "time": "6 P.M. to 12 A.M",
          "first": "$2 Double Wells",
          "second": "$2 Shots",
          "third": "$2 Bombs",
          "fourth": "$2 Appetizer"
        }
        ]
      },
    {
      "id": "2",
      "name": "Fieldhouse",
      "latitude": "38.9517° N",
      "longitude": "92.3249° W",
      "hours": "11:00 A.M. to 1:30 A.M.",
      "deals": [
        {
          "time": "3 P.M. to 7 P.M.",
          "first": "$6 Well Pitchers",
          "second": "$8 Deep Eddy's Pitchers",
          "third": "$15 Domestic Towers",
          "fourth": "$25 Craft Beer Towers"
        },
        {
          "time": "9 P.M. to 12 P.M.",
          "first": "$2 Double Wells",
          "second": "$2 Aluminums"
        }
      ]
    }
    {
      "id": "3",
      "name": "MyHouse",
      "latitude": "38.9499° N",
      "longitude": "92.3300° W",
      "hours": "8 P.M. to 1 A.M.",
      "deals": [
        {
          "time": "7 P.M. to 12 A.M.",
          "first": "$2 Bottles",
          "second": "$3 Jameson",
          "third": "$4 Car Bombs"
        }
      ]
    }
  ]
}`

**Data Types**

`struct Bar:Hashable,Codable{
    let name: String
    let id:Int
    let date: Date
    let coordinate:Coordinate
    let hours: String
    let imageURL: String
    var deals:[Deal]

    enum CodingKeys: String, CodingKey{
        case name
        case id
        case date
        case coordinate = "coords"
        case hours = "hoursOpen"
        case imageURL
        case deals
      }
    }

    struct Deal:Hashable, Codable{
      let hours: String
      let deals: [String]
    }

    struct Coordinate:Hashable,Codable{
      var latitude:Double
      var longitude:Double
    }`
