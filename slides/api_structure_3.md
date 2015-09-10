## バージョニング

* urlにバージョンを含んでいる
```ruby
namespace :api do
    namespace :v1 do
        resources :travels, only: %i(index show)
        resources :places, only: %i(index)
    end
end
```
* よくあるやつ
* 非互換が発生した場合、随時バージョン変えてる
