{% highlight crystal %}
class Person
  getter name : String
  getter age  : Int32
  
  def initialize(@name : String, @age : Int32)
  end 
  
  def has_instance_var?(name) : Bool
    {{ @type.instance_vars.map &.name.stringify }}.includes? name
  end
end

person = Person.new "John", 30
person.has_instance_var?("name") #=> true
person.has_instance_var?("birthday") #=> false
{% endhighlight %}
