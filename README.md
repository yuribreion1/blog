# Ponto importante para `build`

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