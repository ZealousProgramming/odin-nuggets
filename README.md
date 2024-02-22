# odin-nuggets

A collection of snippets on how to do something in odin

## Table of Contents

- [u16 from a [^]u8](#u16-from-a-u8)
- [Get type of struct member](#get-type-of-struct-member)

#### u16 from a [^]u8:

```go
import "core:encoding/endian"
some_data: [^]u8
// ... magically is populated

// Option 1
target_byte_offset := 0
target_byte_length := 2
data, ok := endian.get_u16(some_data[target_byte_offset:target_byte_length])

// Option 2
//data := (^u16)(event.packet.data)^
```

#### Get type of struct member:

```go
SomeStruct :: struct {
    eat_cheese: boolean,
}
// Option 1:
import "base:intrinsics"

intrinsics.type_field_type(Struct, "field_name").
+ intrinsics.type_elem_type(Field_Type)

// Option 2:
type_of(SomeStruct.eat_cheese)
```
