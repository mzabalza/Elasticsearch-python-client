# Elasticsearch-python-client
List of common instructions to create, index, delete, edit data into elasticsearch

### Connection
```python
es = Elasticsearch([{
    'host': host,
    'port': port,
}])
```
### Delete Indices
```python
es.indices.delete(index='test')
```
### Create Indices

```python
es.indices.create(
    index='test',
    body=mapping # optional
)
```
```python
mapping = {
    "mappings": {
        "properties": {
            "title": { "type": 'keyword' },
            "author": { "type": 'keyword' },
            "page": { "type": 'integer' },
            "paragraph": { "type": 'integer' },
            "text": { "type": 'text' }
        }
    }
}
```
### Ingest document
```python
es.index(index='test', body=data)
data = {
    'title': title,
    'author': author,
    'text': p,
    'page': i + 1,
    'paragraph': j
}
```

