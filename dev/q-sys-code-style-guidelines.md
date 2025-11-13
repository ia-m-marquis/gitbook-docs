---
description: Code Styling Guidelines for X-Stage Q-SYS Script and Plugin creation.
---

# Q-SYS Code Style Guidelines

## Code Naming

* **PascalCase** (UpperCamelCase)
  * Global variables
  * Controls
  * Functions
  * Objects/Classes
* **camelCase**
  * Local variables
  * Public methods
* **\_camelCase**
  * Private and protected methods

## Annotations

All functions and methods shall be annotated using the [luals (Lua Language Server)](https://luals.github.io/wiki/annotations/) annotations.

Basic annotations (`@type` , `@class` and `@private` / `@protected`) **MUST** be used, if applicable. All other annotions may be used and are optional.

### Examples

<details>

<summary>Example (function and var definition)</summary>

```lua
---@type number
local count = 10

---@type fun(value: number): boolean
function IsEven(value)
    return value % 2 == 0
end
```

</details>

<details>

<summary>Example (oop and inheritance)</summary>

```lua
---@class Animal
---@field protected name string
---@field protected age number
---@field protected alive boolean
local Animal = {}
Animal.__index = Animal

---@param name string
---@param age number
---@return Animal
function Animal:new(name, age)
    local obj = setmetatable({}, self)

    obj.name = name
    obj.age = age

    obj.alive = true

    return obj
end

-- private method - for internal use
---@private
---@param years number
function Animal:_addAge(years)
    self.age = self.age + years
end

-- public method
---@return string
function Animal:speak()
    return self.name .. " makes a sound."
end

-- public method
function Animal:birthday()
    self:_addAge(1)

    print(self.name .. " celebrates his birthday and is now " .. self.age .. ".")
end

-- derived class
---@class Dog : Animal
---@field private breed string
local Dog = setmetatable({}, {__index = Animal})
Dog.__index = Dog

---@param name string
---@param age number
---@param breed string
---@return Dog
function Dog:new(name, age, breed)
    local obj = setmetatable({}, self)

    obj.name = name
    obj.age = age
    obj.breed = breed

    return obj
end

-- override parent method
---@return string
function Dog:speak()
    return self.name .. " barks."
end

-- example
local dog = Dog:new("Rex", 3, "labrador")
print(dog:speak())
dog:birthday()
```

</details>

## Script Header

```
----------------------------------  X-Stage  ----------------------------------
-- 
-- [Script Name]
--
-- Description:   [Brief description of the script's functionality]
--
-- Version:       [V.x.x.x.x]
-- Date:          [DD.MM.YYYY]
-- Author:        [Your Name]
--
-------- Copyright (c) 2025 Industrial Arts GmbH. All rights reserved. --------
```
