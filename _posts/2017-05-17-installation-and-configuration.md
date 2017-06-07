---
layout: post
title:  "Установка и настройка"
categories: [tool]
---

Для установки jekyll нам потребуется ruby. Официальные доки по установке, настройке и наличествующим плагинам размещены на jekyllrb.com.


{% highlight javascript %}
$ gem install jekyll
$ jekyll new myblog && cd myblog
$ jekyll build && jekyll serve
{% endhighlight %}


После чего можно смело пройти по адресу http://localhost:4000 и насладиться видом своего нового бложека. 
Имейте ввиду, что стили могут не отобразиться из-за дефолтных настроек в _config.yml. Мы вернёмся к этому чуть позже.