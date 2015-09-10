## garage

* アクセス制御はinitializerで定義出来る
```ruby
Garage::TokenScope.configure do
    register :public, desc: "accessing publicly available data" do
        access :read, Recipe
    end

    register :read_post, desc: "reading blog post" do
        access :read, Post
    end
end
```
