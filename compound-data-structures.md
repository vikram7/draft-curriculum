## Compound Data Structures

We've covered basic arrays and hashes, but it's rare that as software developers we will have to deal with such basic data structures in real-world applications. What we will typically see are more complex data structures, which are often deeply nested versions of the basic data structures we've covered. For example, JavaScript Object Notation, or JSON, is a format that is typically used in API calls. This format is an example of the kind of compound data structure a software developer would see on a regular basis. The Yelp search [API](http://www.yelp.com/developers/documentation/v2/search_api) returns a JSON response that can look like the following:

```ruby
response =
{
  "businesses": [
    {
      "categories": [
        [
          "Local Flavor",
          "localflavor"
        ],
        [
          "Mass Media",
          "massmedia"
        ]
      ],
      "display_phone": "+1-415-908-3801",
      "id": "yelp-san-francisco",
      "is_claimed": true,
      "is_closed": false,
      "image_url": "http://s3-media2.ak.yelpcdn.com/bphoto/7DIHu8a0AHhw-BffrDIxPA/ms.jpg",
      "location": {
        "address": [
          "140 New Montgomery St"
        ],
        "city": "San Francisco",
        "country_code": "US",
        "cross_streets": "3rd St & Opera Aly",
        "display_address": [
          "140 New Montgomery St",
          "(b/t Natoma St & Minna St)",
          "SOMA",
          "San Francisco, CA 94105"
        ],
        "neighborhoods": [
          "SOMA"
        ],
        "postal_code": "94105",
        "state_code": "CA"
      },
      "mobile_url": "http://m.yelp.com/biz/4kMBvIEWPxWkWKFN__8SxQ",
      "name": "Yelp",
      "phone": "4159083801",
      "rating_img_url": "http://media1.ak.yelpcdn.com/static/201012161694360749/img/ico/stars/stars_3.png",
      "rating_img_url_large": "http://media3.ak.yelpcdn.com/static/201012161053250406/img/ico/stars/stars_large_3.png",
      "rating_img_url_small": "http://media1.ak.yelpcdn.com/static/201012162337205794/img/ico/stars/stars_small_3.png",
      "review_count": 3347,
      "snippet_image_url": "http://s3-media2.ak.yelpcdn.com/photo/LjzacUeK_71tm2zPALcj1Q/ms.jpg",
      "snippet_text": "Sometimes we ask questions without reading an email thoroughly as many of us did for the last event.  In honor of Yelp, the many questions they kindly...",
      "url": "http://www.yelp.com/biz/yelp-san-francisco",
      "menu_provider": "yelp",
      "menu_date_updated": 1317414369
    }
  ],
  "region": {
    "center": {
      "latitude": 37.786138600000001,
      "longitude": -122.40262130000001
    },
    "span": {
      "latitude_delta": 0.0,
      "longitude_delta": 0.0
    }
  },
  "total": 10651
}
```

Being able to deal with compound data structures like the one above is an essential skill to have as a software developer. What would be the best way to deal with the JSOn above? As all engineers do, by breaking a problem down into smaller problems, or in this case, smaller data structures. Let's examine less complicated compound data structures in order to do this.


```ruby
people =
{
  "Marilyne Bradtke" => {
       "phone" => "894.855.7335",
     "company" => "Murray-Mills",
    "children" => [
        "Turner",
        "Amari"
    ]
  }
}
```

What can we say about `people`? It is a hash which has one key of `Marilyne Bradtke`. That key points to a value, which is another hash that has multiple keys of `phone`, `company`, and `children`. We can test all this in ruby.

```ruby
people.keys
=> ["Marilyne Bradtke"]

people["Marilyne Bradtke"]
=> {"phone"=>"894.855.7335", "company"=>"Murray-Mills", "children"=>["Turner", "Amari"]}

people["Marilyne Bradtke"].keys
=> ["phone", "company", "children"]
```

As you can see, you can start chaining together methods when parsing a compound data structure. Let's play with this a little more.

What is Marilyne Bradtke's phone number?

```ruby
people["Marilyne Bradtke"]["phone"]
=> "894.855.7335"
```

What company does Marilyne work for?

```ruby
people["Marilyne Bradtke"]["company"]
=> "Murray-Mills"
```

How many children does Marilyne have?

```ruby
people["Marilyne Bradtke"]["children"].count
=> 2
```

What is the name of Marilyne's first child?

```ruby
people["Marilyne Bradtke"]["children"].first
=> "Turner"
```

For more practice parsing through compound data structures, run `rubies` from your terminal by installing the [rubies](https://github.com/vikram7/rubies) gem:

```
gem install rubies
rubies
```


