instructions to follow for most of the cases

These are just for testing purposes

get all data using curl:
curl -X GET "http://localhost:9200/transactions/_search?pretty" -H 'Content-Type: application/json' -d'
{
    "query": {
        "match_all": {}
    }
}'
get data pretty:
curl -X GET "http://localhost:9200/transactions/_search?pretty"




post data using curl:
curl -X POST "http://localhost:9200/transactions/_doc/2" -H 'Content-Type: application/json' -d'
{
    "date": "2023-06-02",
    "amount": 200
}'

clear the whole database
curl:
curl -X DELETE "http://localhost:9200/*" deletes whole base including idices

python:
es.delete_by_query(index="*", body={"query": {"match_all": {}}})
print("All documents deleted, indices are retained.")

delete specific indices
curl -X DELETE "http://localhost:9200/transactions/"  where "transactions" is a index

delete all data by retaining indices:

curl -X POST "http://localhost:9200/_all/_delete_by_query" -H 'Content-Type: application/json' -d'
{
  "query": {
    "match_all": {}
  }
}'
