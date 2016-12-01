---
layout: post
title: HOWTO Create a simple parent-child form in Rails 3.1
date: 2011-08-24 16:44:22.000000000 +01:00
---
I'm finding Rails quite difficult conceptually. People tell me one day the light will dawn and it will all seem perfectly natural. At the moment though it seems like there's 1000 ways to achieve any given objective, but only one <strong>right</strong> one. If you choose one of the other 999 then you're in a world of manual coding as a result.

I couldn't find a really basic example of nested forms: a parent record with an arbitrary number of child records. Here's my attempt to create the simplest possible parent-child forms, with the minimum configuration and the maximum convention. Rails experts: I'd love to reduce this even further - please give me any suggestions for doing so.

The resulting forms can be cloned directly from <a href="https://github.com/moo-li/Simple-parent-child-forms-in-Rails-3.1">https://github.com/moo-li/Simple-parent-child-forms-in-Rails-3.1</a>, but here's how to create them yourself:
<ol>
	<li>At the command prompt, create a new Rails application:
<code>rails new myapp</code> (where <code>myapp</code> is the application name). If you want HTML5
goodness then <code>rails new myapp -m https://github.com/russfrisch/h5bp-rails/raw/master/h5bp.rb</code>.</li>
	<li><code>cd myapp</code></li>
	<li><code>rails g scaffold Mom name:string</code></li>
	<li><code>rails g model Kid name:string mom:references</code></li>
	<li>Add the following lines to <code>app/models/mom.rb</code>
<pre>has_many :kids, :dependent =&gt; :destroy
accepts_nested_attributes_for :kids, :allow_destroy =&gt; :true</pre>
</li>
	<li><code>rake db:migrate</code></li>
	<li>In <code>config/routes.rb</code>, change <code>resources :moms</code>to
<pre>resources :moms do
  resources :kids
end</pre>
</li>
	<li><code>rails g controller Kids</code></li>
	<li>Add the following methods to <code>app/controllers/kids_controller.rb</code>
<pre>def create
  @mom = Mom.find(params[:mom_id])
  @kid = @mom.kids.create(params[:kid])
  redirect_to mom_path(@mom)
end

def destroy
  @mom = Mom.find(params[:mom_id])
  @kid = @mom.kids.find(params[:id])
  @kid.destroy
  redirect_to mom_path(@mom)
end</pre>
</li>
	<li>Add the following lines to <code>app/views/moms/show.html.erb</code> before the line
containing <code>&lt;%= link_to 'Edit', edit_mom_path(@mom) %&gt; |</code>
<pre>&lt;h2&gt;Kids&lt;/h2&gt;
&lt;%= render @mom.kids %&gt;

&lt;h3&gt;Add kid&lt;/h3&gt;
&lt;%= render 'kids/form' %&gt;</pre>
</li>
	<li>Create a file <code>app/views/kids/_kid.html.erb</code>with the following code:
<pre>&lt;p&gt;
  &lt;strong&gt;Kid:&lt;/strong&gt;
  &lt;%= kid.name %&gt;
  &lt;%= link_to 'Remove', [kid.mom, kid], :confirm =&gt; 'Really remove kid?', :method =&gt; :delete %&gt;
&lt;/p&gt;</pre>
</li>
	<li>Create a file <code>app/views/kids/_form.html.erb</code>with the following code:
<pre>&lt;%= form_for([@mom, @mom.kids.build]) do |f| %&gt;
  &lt;div class="field"&gt;
    &lt;%= f.label :name %&gt; &lt;%= f.text_field :name %&gt;
  &lt;/div&gt;

  &lt;div class="actions"&gt;
    &lt;%= f.submit %&gt;
  &lt;/div&gt;
&lt;% end %&gt;</pre>
</li>
	<li><code>rails s</code></li>
	<li>Point your browser to <code>https://localhost:3000/moms</code>.</li>
</ol>
