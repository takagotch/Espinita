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
=> [{},
  {},
  {}]
  
my_model.histroy_from_audits_for([:name, :settings])
=> [{},
  {}, {}]

model.name
model.setings
model.histroy_from_audits_for(["name, :settings])
model.restore_attributes([:name, :settings], DateTime.now = 57.days)
model.name
model.settings

```


```
```

