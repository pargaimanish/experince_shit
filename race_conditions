## Race Condition Problem with `$set`

1. **Read** `inG` from the database (e.g., `inG = 5`)
2. **Calculate** in your Node.js code: `5 + 1 = 6`
3. **Write** `inG = 6` back to the database

The problem arises if **two requests happen at nearly the same time:**

```
Request A reads  inG = 5
Request B reads  inG = 5   ← reads before A has written
Request A writes inG = 6
Request B writes inG = 6   ← should be 7, but it's 6!
```

One increment is **lost**.

---

## Why `$inc` is Safer

With `$inc`, you're telling MongoDB *"add 1 to whatever the current value is"* — the read and write happen together **inside MongoDB itself**, as a single operation. No value is read into your app first.

```
Request A tells MongoDB: increment inG by 1  →  inG becomes 6
Request B tells MongoDB: increment inG by 1  →  inG becomes 7  ✓
```

MongoDB handles the math, so two simultaneous requests can't interfere with each other. That's what "atomic" means here — the operation is indivisible, it can't be interrupted halfway through.


Race condition here:

const updateInN = await Cafes.findOneAndUpdate(
  { cafename: `${cafeName}` },
  { $set: { inG: inG + 1 } },
  { new: true }
);


solve through atomic:

const updateInN = await Cafes.findOneAndUpdate(
  { cafename: cafeName },
  { $inc: { inG: 1 } },
  { new: true }
);

