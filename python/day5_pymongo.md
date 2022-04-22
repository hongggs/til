# python-pymongo

## pymongo 활용

프로젝트를 진행하면서 최신순으로 데이터를 뽑아오거나 가장 최신 데이터 하나만 가지고오는 코드를 짜야하는 일이 있었다.
pymongo를 처음 다루어보았는데 기억하기위해 적어놓았다.

1) pymongo 최신순으로 정렬 

```db.collection.find({}, {'_id': False}).sort('_id', -1)```

2) pymongo 가장 최신 데이터 하나만 가져오기

```db.collection.find({}, sort=[('_id', -1)]).limit(1)```

이외에 프로젝트에서 사용된 pymongo 함수를 찾아보자면

3) 찾기

      - 특정 단어가 포함된 것 찾기 
            
      ```db.collection.find({'field': {'$regex': query_receive}}, {'_id': False})```
      - 하나만 찾기

      ```db.collection.find_one({'field': 값}, {'_id': False})```

4) 삽입 (하나만)

```db.collection.insert_one(doc)```

