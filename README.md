[![Gem Version](https://badge.fury.io/rb/area_cn.png)](http://badge.fury.io/rb/area_cn)
## 地区选择插件(测试中) 
  整理多种地区选择器:

  1. select-ul 模拟下拉菜单
  2. select(done,testing)

## Example
  [Online Demo](http://112.124.38.145:9292).

##Features
  1. 支持bootstrap  
  2. 支持simple_form
  3. 支持select和select-ul


##Installation
Add it to your Gemfile:
```ruby
gem 'area_select_cn',:git=>"git@github.com:Kehao/area_select_cn.git"
```

And then execute:
```console
bundle install
```

Add it to your application.js:

```console
// select
//= require area_select_cn/jquery.district-ul
// select-ul
//= require area_select_cn/jquery.district-ul
```

if you want to use the default theme, add it to your application.css:
```console
*= require area_select_cn/district-ul
```

## FormHelper
###form_tag
```erb

<%= form_tag "" do %>
<!-- select -->
  <%= district_select(:company,:region_code,"331000") %>
<!-- select-ul -->
  <%= district_select_ul(:company,:region_code,"331000") %>
<% end %>
```

###form_for
```erb
<%= form_for Company.new,:builder => AreaSelectCn::Helpers::FormBuilder do |f| %>
<!-- select -->
  <%= f.district_select :region_code%>
<!-- select-ul -->
  <%= f.district_select_ul :region_code%>
<%end%>
```

###simple_form_for
```erb
<%= simple_form_for Company.new,:html => { :class => 'form-horizontal' } do |f| %>
<!-- select -->
  <%= f.input :region_code,:as => :district_select %>
<!-- select-ul -->
  <%= f.input :region_code,:as => :district_select_ul %>
<% end %>
```

###province,city,district select helper
```erb
<!-- select,select-ul适用 -->
<!-- form_tag -->
<%= district_select_ul(:company,:region_code,"331000") %>
<%= city_select_ul(:company,:region_code,"331000") %>
<%= province_select_ul(:company,:region_code,"331000") %>

<!-- form_for -->
<%= f.district_select_ul :region_code %>
<%= f.city_select_ul :region_code %>
<%= f.province_select_ul :region_code %>

<!-- simple_form_for -->
<%= f.input :region_code,:as => :district_select_ul %>
<%= f.input :region_code,:as => :city_select_ul %>
<%= f.input :region_code,:as => :province_select_ul %>
```

##Theme(select-ul适用)
  1. default
  2. bootstrap

if you want to use the default theme, add it to your application.css:
```console
*= require area_select_cn/district-ul
```
if you want to use bootstrap theme, you should import bootstrap css.

```erb
<!-- form_tag -->
<%= district_select_ul(:company,:region_code,"331000",:theme=>:bootstrap) %>

<!-- form_for -->
<%= f.district_select_ul :region_code,:theme=>:bootstrap,:prompt_class=>"btn btn-success"%>

<!-- simple_form_for,如果SimpleForm.wrapper等于:bootstrap，默认样式为:bootstrap -->
<%= f.input :region_code,:as => :district_select_ul %>
```
## Resources
* Chosen(http://harvesthq.github.io/chosen/)
* X-editable(http://vitalets.github.io/x-editable/demo.html)
* Jquery-addresspicker(http://xilinus.com/jquery-addresspicker/demos/index.html)
* Jquery-Autocomplete(https://github.com/devbridge/jQuery-Autocomplete)
* Jquery-tokeninput(https://github.com/loopj/jquery-tokeninput)
* Jquery-ui(http://jqueryui.com/autocomplete/)
* Select2(http://ivaynberg.github.io/select2/)
* typeahead.js(https://github.com/twitter/typeahead.js/)


##Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

