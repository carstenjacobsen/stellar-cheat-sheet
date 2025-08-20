# CLI Invoke Argument Formatting
WHen you invoke commands in the Stellar CLI, arguments have to be formatted a certain way. This cheat sheet shows how to format different types of arguments.

| Type         | Example Format                                | Notes |
|--------------|-----------------------------------------------|-------|
| **Integer (i32/u32, i64/u64)** | `42` | Auto-detected as int |
| **Big Int (i128/u128)** | `1234567890123456789` |  |
| **Boolean**  | `true` <br> `false` | Lowercase only |
| **String**   | `"hello world"` | Use quotes for spaces |
| **Symbol**   | `transfer` <br> `USD` | Cheap identifier, like enums |
| **Address**  | `GCFX...XYZ` <br> `CABC...DEF` | Works for G-accounts & C-contracts |
| **Vector (Array)** | `'[1,2,3]'` <br> `'[buy, sell]'` | Enclose in `[...]` |
| **Map (Key-Value)** | `'{name:"Alice"}'` <br> `'{age:30, active:true}'` | Enclose in `{...}` |
| **Struct (Custom type)** | `'{name:"Bob", age:25}'` | Serialize as map with `field:value` |
| **Nested**   | `'[{user:"Alice"}, {user:"Bob"}]'` | Supports nesting maps/vectors |

