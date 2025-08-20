# CLI Invoke Argument Formatting
WHen you invoke commands in the Stellar CLI, arguments have to be formatted a certain way. This cheat sheet shows how to format different types of arguments.

| Type         | Example Format                                | Notes |
|--------------|-----------------------------------------------|-------|
| **Integer (i32/u32/i64/u64)** | `--arg 42` | Auto-detected as int |
| **Big Int (i128/u128)** | `--arg i128:1234567890123456789` <br> `--arg u128:9876543210123456789` | Must prefix with type |
| **Boolean**  | `--arg true` <br> `--arg false` | Lowercase only |
| **String**   | `--arg "hello world"` | Use quotes for spaces |
| **Symbol**   | `--arg sym:transfer` <br> `--arg sym:USD` | Cheap identifier, like enums |
| **Address**  | `--arg address:GCFX...XYZ` <br> `--arg address:CABC...DEF` | Works for G-accounts & C-contracts |
| **Bytes**    | `--arg 0xdeadbeef` | Hex-encoded |
| **Vector (Array)** | `--arg '[1,2,3]'` <br> `--arg '[sym:buy, sym:sell]'` | Enclose in `[...]` |
| **Map (Key-Value)** | `--arg '{sym:name:"Alice"}'` <br> `--arg '{sym:age:30, sym:active:true}'` | Enclose in `{...}` |
| **Struct (Custom type)** | `--arg '{sym:name:"Bob", sym:age:25}'` | Serialize as map with `sym:field:value` |
| **Nested**   | `--arg '[{sym:user:"Alice"}, {sym:user:"Bob"}]'` | Supports nesting maps/vectors |

