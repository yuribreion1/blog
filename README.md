# Aqui a brincadeira nasceu

- `- jekyll b`

# Aqui a brincadeira começou

- ` jekyll s`

## Ponto importante para `build`

1 - Instalar o Gem
`gem install jekyll-paginate`

2 -	Dentro do `_config.yml`
``` ruby
plugins:
  - jekyll-paginate
paginate: 5
```

3 - Dentro do Gemfile
``` ruby
group :jekyll_plugins do
   gem "jekyll-paginate"
end
```

- Gemfile
``` ruby 
source "https://rubygems.org"
gem "rake"
ruby "2.5.3"
```

- Rakefile
``` ruby
namespace :assets do
  task :precompile do
    puts `bundle exec jekyll build`
  end
end
```