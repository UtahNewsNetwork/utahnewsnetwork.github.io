---
layout: page
title: News
permalink: /News
comments: false
---

<div class="row justify-content-between">
<div class="col-md-8 pr-5">    
    
<div class="site-content">   
    
<div class="container">
    

    
<!-- Content
================================================== --> 
    {{ content }}
</div>

{% if site.mailchimp-list %}
<!-- Bottom Alert Bar
================================================== -->
<div class="alertbar" id="Alertbar">
	<div class="container text-center">
		<span><img src="{{ site.baseurl }}/{{ site.logo }}" alt="{{site.title}}"> &nbsp; Never miss a <b>story</b> from us, subscribe to our newsletter</span>
        <form action="{{site.mailchimp-list}}" method="post" name="mc-embedded-subscribe-form" class="wj-contact-form validate" target="_blank" novalidate>
            <div class="mc-field-group">
            <input type="email" placeholder="Email" name="EMAIL" class="required email" id="mce-EMAIL" autocomplete="on" required>
            <input type="submit" value="Subscribe" name="subscribe" class="heart">
            </div>
        </form>
	</div>
</div>    
{% endif %}
    
</div>

<!-- Categories Jumbotron
================================================== -->
<div class="jumbotron fortags" id="Jumbo">
	<div class="d-md-flex h-100">
		<div class="col-md-4 transpdark align-self-center text-center h-100">
            <div class="d-md-flex align-items-center justify-content-center h-100">
                <h2 class="d-md-block align-self-center py-1 font-weight-light">Explore <span class="d-none d-md-inline">→</span></h2>
            </div>
		</div>
		<div class="col-md-8 p-5 align-self-center text-center">      
            {% assign categories_list = site.categories %}
            {% if categories_list.first[0] == null %}
                {% for category in categories_list %}
                    <a href="{{site.baseurl}}/categories#{{ category | url_escape | strip | replace: ' ', '-' }}">{{ category | camelcase }} ({{ site.tags[category].size }})</a>
                {% endfor %}
            {% else %}
                {% for category in categories_list %}                        
                    <a href="{{site.baseurl}}/categories#{{ category[0] | url_escape | strip | replace: ' ', '-' }}">{{ category[0] | camelcase }} ({{ category[1].size }})</a>
                {% endfor %}
            {% endif %}
            {% assign categories_list = nil %}
		</div>
        

        
	</div>
</div>
    


</div>
</div>
