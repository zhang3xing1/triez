A simple proof-of-concept full text search server with *triez*, *sqlite* and *drb*

install required gems:

``` ruby
gem ins triez sqlite3
```

start server:

``` bash
ruby server.rb
```

client usage:

```ruby
require './client'
c = Client.new 'localhost', 8787
c.insert id, document_content
c.query a_phrase
```

An experiment of indexing 30M text of 130 documents took about 1 minute (mostly sqlite time) and 190M memory in index. Once the index is finished, the query is super fast. Loading index from database is also quite fast.
