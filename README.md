# LuaClass
Another Lua OOP implementation

This implementation was made to be fast, simple and have clear syntax. Objects, created with `class` constructor doesn't use metatables, so you are free to use it as you wish. Keep in mind, that class constructor is looking like `class(parents)(impl)` with unnecessary second `()`, so you if you wanted to create class without parents(Whyever would you need that? You can use any table as parent) you should do it like in first line of example below.

Here's a short demo of usage:
```lua
Parent = class(){value = "default"}

Mixin = {}

function Mixin:method(value) 
  self.value = value 
end

Child = class(Parent, Mixin){
  value = "another", 
  init = function(self, value) 
    self:method(value) 
  end
}
```
