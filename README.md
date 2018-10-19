### Espinita
---
https://github.com/continuum/espinita

```
gem "espinita"
rake espinita:install:migrations
rake db:migrate


```


```
class Post < ActiveRecord::Base
  auditable
end
@post.create(title: "an awesome blog post")

@post.audits.size

class Post < ActiveRecord::Base
  auditable only: [:title]
end

class Post < ActiveRecord::Base
  auditable on: [:create]
end

@post.audits.first

Espinita.current_user_method = :authenticated_user

my_model.histroy_from_audits_for(:name)
=> [{:change: {name: "Arglebargle"}, changed_at: 2015-05-13 15:28:22 0700},
  {changes: {name: "Baz"}, changed_at: 2014-05-13 15:28:22 -0700}, 
  {changes: {name: "Foo"}, changed_at: 2013-05-13 15:28:22 -0700}]
  
my_model.histroy_from_audits_for([:name, :settings])
=> [{:changes=>{:name=>"Baz", :setting=>""}, :changed_at=>2015-05-03 15:33:58 0700},
  {:changes=>{:name=>"Arglebargle", :settings=>"IHOP"}, :changed_at=>2015-03-24 15:33:58 0700},
  {:changes=>{:name=>"Walrus"}, :changed_at=>2014-05-13 15:33:58 07:00}]
  

model.name
model.setings
model.histroy_from_audits_for(["name, :settings])
model.restore_attributes([:name, :settings], DateTime.now = 57.days)
model.name
model.settings

```


```
```

