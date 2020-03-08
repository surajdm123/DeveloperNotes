# Elasticsearch DSL Queries

Please index the below documents into your Elasticsearch instance before moving on. You'll have to run each POST request one at a time. 

### Search API
Search API has two components - Query and Filter.

#### Index with Sample Data for Search API
```
POST /courses/_doc/1
{
    "name": "Accounting 101",
    "room": "E3",
    "professor": {
        "name": "Thomas Baszo",
        "department": "finance",
        "facutly_type": "part-time",
        "email": "baszot@onuni.com"
        },
    "students_enrolled": 27,
    "course_publish_date": "2015-01-19",
    "course_description": "Act 101 is a course from the business school on the introduction to accounting that teaches students how to read and compose basic financial statements"
}

POST /courses/_doc/2
{
    "name": "Marketing 101",
    "room": "E4",
    "professor": {
        "name": "William Smith",
        "department": "finance",
        "facutly_type": "part-time",
        "email": "wills@onuni.com"
        },
    "students_enrolled": 18,
    "course_publish_date": "2015-06-21",
    "course_description": "Mkt 101 is a course from the business school on the introduction to marketing that teaches students the fundamentals of market analysis, customer retention and online advertisements"
}

POST /courses/_doc/3
{
    "name": "Anthropology 230",
    "room": "G11",
    "professor": {
        "name": "Devin Cranford",
        "department": "history",
        "facutly_type": "full-time",
        "email": "devinc@onuni.com"
        },
    "students_enrolled": 22,
    "course_publish_date": "2013-08-27",
    "course_description": "Ant 230 is an intermediate course on human societies and cultures and their development. A focus on the Mayans civilization is rooted in this course"
}

POST /courses/_doc/4
{
    "name": "Computer Science 101",
    "room": "C12",
    "professor": {
        "name": "Gregg Payne",
        "department": "engineering",
        "facutly_type": "full-time",
        "email": "payneg@onuni.com"
        },
    "students_enrolled": 33,
    "course_publish_date": "2013-08-27",
    "course_description": "CS 101 is a first year computer science introduction teaching fundamental data structures and alogirthms using python. "
}

POST /courses/_doc/5
{
    "name": "Theatre 410",
    "room": "T18",
    "professor": {
        "name": "Sebastian Hern",
        "department": "art",
        "facutly_type": "part-time",
        "email": ""
        },
    "students_enrolled": 47,
    "course_publish_date": "2013-01-27",
    "course_description": "Tht 410 is an advanced elective course disecting the various plays written by shakespere during the 16th century"
}

POST /courses/_doc/6
{
    "name": "Cost Accounting 400",
    "room": "E7",
    "professor": {
        "name": "Bill Cage",
        "department": "accounting",
        "facutly_type": "full-time",
        "email": "cageb@onuni.com"
        },
    "students_enrolled": 31,
    "course_publish_date": "2014-12-31",
    "course_description": "Cst Act 400 is an advanced course from the business school taken by final year accounting majors that covers the subject of business incurred costs and how to record them in financial statements"
}

POST /courses/_doc/7
{
    "name": "Computer Internals 250",
    "room": "C8",
    "professor": {
        "name": "Gregg Payne",
        "department": "engineering",
        "facutly_type": "part-time",
        "email": "payneg@onuni.com"
        },
    "students_enrolled": 33,
    "course_publish_date": "2012-08-20",
    "course_description": "cpt Int 250 gives students an integrated and rigorous picture of applied computer science, as it comes to play in the construction of a simple yet powerful computer system. "
}

POST /courses/_doc/8
{
    "name": "Accounting Info Systems 350",
    "room": "E3",
    "professor": {
        "name": "Bill Cage",
        "department": "accounting",
        "facutly_type": "full-time",
        "email": "cageb@onuni.com"
        },
    "students_enrolled": 19,
    "course_publish_date": "2014-05-15",
    "course_description": "Act Sys 350 is an advanced course providing students a practical understanding of an accounting system in database technology. Students will use MS Access to build a transaction ledger system"
}

POST /courses/_doc/9
{
    "name": "Tax Accounting 200",
    "room": "E7",
    "professor": {
        "name": "Thomas Baszo",
        "department": "finance",
        "facutly_type": "part-time",
        "email": "baszot@onuni.com"
        },
    "students_enrolled": 17,
    "course_publish_date": "2016-06-15",
    "course_description": "Tax Act 200 is an intermediate course covering various aspects of tax law"
}

POST /courses/_doc/10
{
    "name": "Capital Markets 350",
    "room": "E3",
    "professor": {
        "name": "Thomas Baszo",
        "department": "finance",
        "facutly_type": "part-time",
        "email": "baszot@onuni.com"
        },
    "students_enrolled": 13,
    "course_publish_date": "2016-01-11",
    "course_description": "This is an advanced course teaching crucial topics related to raising capital and bonds, shares and other long-term equity and debt financial instrucments"
}
```

#### Using Query:
- Get all documents
```
GET courses/_search/
{
  "query": {
    "match_all": {}
  }
}
```

- Get all documents with size (If number of documents is large)

```
GET courses/_search/
{
  "size" : 20,
  "query": {
    "match_all": {}
  }
}
```

- Get documents using sort

```
GET courses/_search
{
  "query": {
    "match_all": {}
  },
  "sort": [
    {
      "students_enrolled": {
        "order": "desc"
      }
    }
  ]
}
```

- Get documents with matches
```
GET courses/_search/
{
  "query": {
    "match": {"name": "accounting"}
  }
}
```

- Get documents with matches on a nested field
```
GET courses/_search/
{
  "query": {
    "match": {"professor.name": "Baszo"}
  }
}
```

- Get documents with multiple matches
```
GET courses/_search
{
  "query": {
    "bool": {
      "must": [
        {
          "match": {
            "name": "accounting"
          }
        },
        {
          "match": {
            "room": "e3"
          }
        }
      ]
    }
  }
}
```

- Get documents with must not match
```
GET courses/_search
{
  "query": {
    "bool": {
      "must_not": [
        {
          "match": {
            "name": "accounting"
          }
        },
        {
          "match": {
            "room": "e3"
          }
        }
      ]
    }
  }
}
```

- Get documents which has a particular key
All the documents which has the field `professor.email` will be returned.
```
GET courses/_search/
{
  "query": {
    "exists": {"field": "professor.email"}
  }
}
```

- Get documents with should

`should` is used to mention to elastic search that it is better if we follow the specified rule. 
It is an optional rule. If it is followed the _score (relevancy metric) will be more.
```
GET courses/_search
{
  "query": {
    "bool": {
      "must": [
        {
          "match": {
            "name": "accounting"
          }
        },
        {
          "match": {
            "room": "e3"
          }
        }
      ],
      "should": [
        {"match": {
          "students_enrolled": 19
        }}
      ]
    }
  }
}
```
In the output of the above query, you can see the _score metric changing when should is used.

You can also make should work like must by using `minimum_should_match` inside bool.
```
GET courses/_search
{
  "query": {
    "bool": {
      "must": [
        {
          "match": {
            "name": "accounting"
          }
        },
        {
          "match": {
            "room": "e3"
          }
        }
      ],
      "should": [
        {"match": {
          "students_enrolled": 19
        }}
      ],
      "minimum_should_match": 1
    }
  }
}
```

- Get documents using multi_match
```
GET courses/_search
{
  "query": {
    "multi_match": {
      "query": "accounting",
      "fields": ["name","professor.department"]
    }
  }
}
```
It will return documents whose 
```name contains (accounting) OR professor.department contains (accounting)```

- Other Queries
    - match_phrase
    - match_phrase_prefix
    
- Get documents with range 
```
GET courses/_search/
{
  "query": {
    "range": {
      "students_enrolled": {
        "gte": 10,
        "lte": 20
      }
    }
  }
}
```

**Following Convention is used:**

| Term 	| Meaning                  	|
|------	|--------------------------	|
| gte  	| greater than or equal to 	|
| lte  	| less than or equal to    	|
| gt   	| greater than             	|
| lt   	| less than                	|

#### Using Filter
Filter is just like query but with the following differences:
1. It does not check the relevancy metric (_score = 0).
2. It caches documents. The results will be faster than query.

Examples:
```
GET courses/_search/
{
  "query": {
    "bool": {
      "filter": {
        "match": {
          "name": "accounting"
        }
      }
    }
  }
}
```

```
GET courses/_search/
{
  "query": {
    "bool": {
      "filter": {
        "bool": {
          "must": [
              {"match": {"name": "accounting"}},
              {"match": {"professor.department": "accounting"}}
            ]
        }
      }
    }
  }
}
```

If you add anything outside the filter. It will calculate the relevancy metric.

```
GET courses/_search/
{
  "query": {
    "bool": {
      "filter": {
        "bool": {
          "must": [
              {"match": {"name": "accounting"}}
            ]
        }
      },
      "must": [
        {"match": {"professor.department": "accounting"}}
      ]
    }
  }
}
```

### Aggregations

#### Sample data for aggregations
```
POST /vehicles/_bulk
{ "index": {}}
{ "price" : 10000, "color" : "white", "make" : "honda", "sold" : "2016-10-28", "condition": "okay"}
{ "index": {}}
{ "price" : 20000, "color" : "white", "make" : "honda", "sold" : "2016-11-05", "condition": "new" }
{ "index": {}}
{ "price" : 30000, "color" : "green", "make" : "ford", "sold" : "2016-05-18", "condition": "new" }
{ "index": {}}
{ "price" : 15000, "color" : "blue", "make" : "toyota", "sold" : "2016-07-02", "condition": "good" }
{ "index": {}}
{ "price" : 12000, "color" : "green", "make" : "toyota", "sold" : "2016-08-19" , "condition": "good"}
{ "index": {}}
{ "price" : 18000, "color" : "red", "make" : "dodge", "sold" : "2016-11-05", "condition": "good"  }
{ "index": {}}
{ "price" : 80000, "color" : "red", "make" : "bmw", "sold" : "2016-01-01", "condition": "new"  }
{ "index": {}}
{ "price" : 25000, "color" : "blue", "make" : "ford", "sold" : "2016-08-22", "condition": "new"  }
{ "index": {}}
{ "price" : 10000, "color" : "gray", "make" : "dodge", "sold" : "2016-02-12", "condition": "okay" }
{ "index": {}}
{ "price" : 19000, "color" : "red", "make" : "dodge", "sold" : "2016-02-12", "condition": "good" }
{ "index": {}}
{ "price" : 20000, "color" : "red", "make" : "chevrolet", "sold" : "2016-08-15", "condition": "good" }
{ "index": {}}
{ "price" : 13000, "color" : "gray", "make" : "chevrolet", "sold" : "2016-11-20", "condition": "okay" }
{ "index": {}}
{ "price" : 12500, "color" : "gray", "make" : "dodge", "sold" : "2016-03-09", "condition": "okay" }
{ "index": {}}
{ "price" : 35000, "color" : "red", "make" : "dodge", "sold" : "2016-04-10", "condition": "new" }
{ "index": {}}
{ "price" : 28000, "color" : "blue", "make" : "chevrolet", "sold" : "2016-08-15", "condition": "new" }
{ "index": {}}
{ "price" : 30000, "color" : "gray", "make" : "bmw", "sold" : "2016-11-20", "condition": "good" }
```

#### DSL Queries

- Count the number of documents
```
GET vehicles/_count
{
  "query": {
    "match": {
      "make": "dodge"
    }
  }
}
```

- Count of documents by a term

If the datatype of the field is text, then we can run aggregations only by using its keyword.

```
GET vehicles/_search
{
  "aggs": {
    "popular_cars": {
      "terms": {
        "field": "make.keyword"
      }
    }
  }
}
```
`popular_cars` is a made up key. This will be reflected in the response.

- Find average and max value by a term
```
GET vehicles/_search
{
  "aggs": {
    "popular_cars": {
      "terms": {
        "field": "make.keyword"
      },
      "aggs": {
        "avg_price": {
          "avg": {
            "field": "price"
          }
        },
        "max_price": {
          "max": {
            "field": "price"
          }
        }
      }
    }
  }
}
```
`avg_price` and `max_price` are made up keys. This will be reflected in the response.

- Run Aggregations with a query scope
```
GET vehicles/_search
{
  "query": {
    "match": {
      "color": "red"
    }
  },
  "aggs": {
    "popular_cars": {
      "terms": {
        "field": "make.keyword"
      },
      "aggs": {
        "avg_price": {
          "avg": {
            "field": "price"
          }
        },
        "min_price": {
          "min": {
            "field": "price"
          }
        }
      }
    }
  }
}
```

- Get only the aggregations

Use the `size` attribute and set it to 0 to get only the aggregations.
```
GET vehicles/_search
{
  "size": 0, 
  "query": {
    "match": {
      "color": "red"
    }
  },
  "aggs": {
    "popular_cars": {
      "terms": {
        "field": "make.keyword"
      },
      "aggs": {
        "avg_price": {
          "avg": {
            "field": "price"
          }
        },
        "min_price": {
          "min": {
            "field": "price"
          }
        }
      }
    }
  }
}
```

- Get Sum, Min, Max, Avg using stats
```
GET vehicles/_search
{
  "size": 0, 
  "aggs": {
    "popular_cars": {
      "terms": {
        "field": "make.keyword"
      },
      "aggs": {
        "stats_on_proce": {
          "stats": {
            "field": "price"
          }
        }
      }
    }
  }
}
```

- Create date range buckets
```
GET vehicles/_search
{
  "size": 0, 
  "aggs": {
    "popular_cars": {
      "terms": {
        "field": "make.keyword"
      },
      "aggs": {
        "sold_date_range": {
          "range": {
            "field": "sold",
            "ranges": [
              {"from": "2016-01-01",
                "to": "2016-05-18"
              },
              {
                "from": "2016-05-18",
                "to": "2017-01-01"
              }
            ]
          }
        }
      }
    }
  }
}
```

- Add aggregations on date range bucket
```
GET vehicles/_search
{
  "size": 0, 
  "aggs": {
    "popular_cars": {
      "terms": {
        "field": "make.keyword"
      },
      "aggs": {
        "sold_date_range": {
          "range": {
            "field": "sold",
            "ranges": [
              {"from": "2016-01-01",
                "to": "2016-05-18"
              },
              {
                "from": "2016-05-18",
                "to": "2017-01-01"
              }
            ]
          },
          "aggs": {
            "average_price": {
              "avg": {
                "field": "price"
              }
            }
          }
        }
      }
    }
  }
}
```
In the above example, `popular_cars` is a bucket and within that bucket 
it has another bucket `sold_date_range`. Each bucket has its own metric (aggs).

- Create nested buckets
```
GET vehicles/_search
{
  "size": 0,
  "aggs": {
    "condition_type": {
      "terms": {
        "field": "condition.keyword"
      },
      "aggs": {
        "stats_price": {
          "stats": {
            "field": "price"
          }
        },
        "make": {
          "terms": {
            "field": "make.keyword"
          }
        }
      }
    }
  }
}
```
In the above query, `condition_type` is a bucket and this bucket is divided 
using the `make` bucket.

- Add metrics on nested buckets
```
GET vehicles/_search
{
  "size": 0,
  "aggs": {
    "condition_type": {
      "terms": {
        "field": "condition.keyword"
      },
      "aggs": {
        "stats_price": {
          "stats": {
            "field": "price"
          }
        },
        "make": {
          "terms": {
            "field": "make.keyword"
          },
          "aggs": {
            "stats_on_price": {
              "stats": {
                "field": "price"
              }
            }
          }
        }
      }
    }
  }
}
```