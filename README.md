# t-type-check

```typescript
import T from "t-type-check";

const isDoorData = T({
  type: T("open", "close"),
  data: T.mapOf(T.int, T.bool).optional
});

isDoorData({type: "open", data: {"door1": true, "door2": 20}}) // true

isDoorData({type: "open"}) // true

isDoorData({type: "close", data: {"door3": 32.5}}) // false

const data = {type: "break", data: {"door1": true}}
const doorsData = isDoorData.assert(data, "wrong door format"); // throws error

```