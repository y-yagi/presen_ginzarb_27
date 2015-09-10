## garage

* responseはクラスで定義する
```ruby
class Employee < ActiveRecord::Base
    include Garage::Representer
    belongs_to :division
    has_many :projects
    property :id
    property :title

    property :division, selectable: true
    collection :projects, selectable: true

    link(:division) { division_path(division) }
    link(:projects) { employee_projects_path(self) }

    def self.build_permissions(perms, other, target)
      perms.permits! :read
    end
end
```
* active_model_serializers っぽさある
