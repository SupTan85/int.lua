# int

![https://github.com/SupTan85/int](cover.png)

## Let's unlimit the number in Lua

This module unlock the limit for calculate large number in Lua. *This project is in beta!*

**Support & Verify: Lua 5.2, Lua 5.3, Lua 5.4**\
**Check by [example.lua](example.lua) file**

---

## how to use

Require a module with `require` function in Lua

```lua
local int = require("int")
```

Use this module you should to make a new object

```lua
local int = require("int")

local x = int.new("13") -- input can be a number or string! *recommend to use string*

print(x) -- output: "13"
```

Use [Calculation operators](#operators) to calculate math.

**Note:** only operator that in support

```lua
-- require a module
local int = require("int")

-- build a new int object
local x, y = int.new("20", "10")

print(x + y) -- output: 30
```

---

## feature

- **Calculate**
  - addition `+`
  - subtraction `-`
  - multiplication `*`
  - division `\, \\`
  - modulo `%`
  - power `^`
  - sqrt
- **Equation**
  - equal
  - less than
  - more than

**and more...**

---

## design

This a example inside table of [int object](#int-object)

```lua
local example_int_table = {
    -- digit --
    [1] = 1, -- this a digit block
    [0] = 0,
    [-1] = 1,

    --[[
        << fraction | digit >>
      INDEX: -1 | 0 | 1
      VALUE:  1 : 0 : 1

      TOSTRING: "1.01"
      TONUMBER: 1.01
    ]]
    -- data --
    sign = "+",

    _dlen = -1, -- digit of fraction *this for calculate a fraction* **DO NOT CHANGE. HAVE LIMIT!!**
    _size = 1 -- mean per size of block *just maximum digit per value in the digit block* **DO NOT CHANGE. HAVE LIMIT!!**
}
```

---

## int object

A table but you can call a function with it and can calculate with using operators

**example script:**

```lua
local int = require("int") -- don't forgot to require a module!

local x, y = int.new("12", "14")
print(x + y) -- output: 26
```

**or:**

```lua
local int = require("int") -- don't forgot to require a module!

local x = int.new("14")
if x:eqmore("12") then -- some Lua version will not suport, that why i recommend you to use function.
    print("omg yes") -- output: omg yes
end
```

very easy, right?

---

## function & methods

all function is in version: **build 185**

- **module function**
  - int.abs
  - int.ceil
  - int.cnew
  - int.cround
  - int.eqless
  - int.eqmore
  - int.equal
  - int.exp
  - int.fact
  - int.fdigitlen
  - int.floor
  - int.fmod
  - int.fractionlen
  - int.integerlen
  - int.less
  - int.ln
  - int.max
  - int.min
  - int.modf
  - int.more
  - int.new
  - int.pow
  - int.sign
  - int.sqrt
  - int.tonumber
  - int.tostring
  - int.unm

**Example to call a function:**

```lua
-- require a module.
local int = require("int")

-- build int object.
local x = int.new("14.695")

-- using a custom floor function.
print(int.floor(x, 2)) -- output: 14.69
```

---

- **methods**
  - abs
  - ceil
  - cround
  - eqless
  - eqmore
  - equal
  - exp
  - fact
  - fdigitlen
  - floor
  - fmod
  - fractionlen
  - integerlen
  - less
  - ln
  - max
  - min
  - modf
  - more
  - pow
  - sign
  - sqrt
  - tonumber
  - tostring
  - unm

**Example to call a function:**

```lua
-- require a module.
local int = require("int")

-- build int object.
local x = int.new("14.695")

-- using a custom floor function.
print(x:floor(2)) -- output: 14.69
```

---

## operators

- **Calculation**
  - addition `+`
  - subtraction `-`
  - multiplication `*`
  - division `\`
  - floor division `\\` *-- some version of Lua are not support (Lua 5.3 >=)*
  - modulo `%` *-- some version of Lua are not support (Lua 5.1 >=)*
  - power `^` *-- some version of Lua are not support (Lua 5.1 >=)*

**Example to using a calculation operator:**

```lua
local int = require("int")

local x, y = int.new("4", "2")

print(x / y) -- output: 2
```

**Note:** some version of Lua you can use calculation operator with number & string

---

- **Equation**
  - equal `==`
  - equal or less `<=`
  - equal or more `>=`
  - less than `<`
  - more than `>`

**Example to using a equation operator:**

```lua
local int = require("int")

local x, y = int.new("4", "2")

print(x > y) -- output: true
```

**Note:** some version of Lua you can use equation operator with number & string

---

## limit

- some function won't support a super very large data, however that function i didn't find it. lol
</br>

- Maximum digit of integer is 9223372036854775806
  - Set `_size` to `9` maximum digit of integer is `83010348331692982254 (9223372036854775806 * 9)`

- Maximum digit of fraction is 9223372036854775808
  - Set `_size` to `9` maximum fraction of integer is `83010348331692982263 (9223372036854775808 * 9)`

---

reason why this module name is "int"? because in this module always use integer to calculate math.\
**feel free to use!**

![end](image-d.png)
