# FlyCharm Drops - Simple Version

**Clean. Minimal. Just edit and go.**

---

## How It Works

1. **Edit deals** in `drops-simple.html` (line 95-135)
2. **Save the file**
3. **Done.** Deals update instantly.

---

## Adding a New Deal (30 seconds)

Open `drops-simple.html` and find this section:

```javascript
const deals = [
    {
        route: "Delhi → Dubai",
        price: "₹8,999",
        originalPrice: "₹18,500",
        date: "Dec 15",
        type: "One Way",
        bookingUrl: "https://www.airindia.com"
    },
    // Add more deals here...
];
```

**Copy this template:**
```javascript
{
    route: "City → City",
    price: "₹0,000",
    originalPrice: "₹0,000",
    date: "Dec 15",  // or "Dec 15-22" for round trip
    type: "One Way",  // or "Round Trip"
    bookingUrl: "https://airline.com"
},
```

**Paste it, update the values, save.**

---

## What Each Field Means

| Field | What It Is | Example |
|-------|-----------|---------|
| `route` | Origin → Destination | `"Delhi → Dubai"` |
| `price` | Deal price | `"₹8,999"` |
| `originalPrice` | Regular price | `"₹18,500"` |
| `date` | Travel date(s) | `"Dec 15"` or `"Dec 15-22"` |
| `type` | Trip type | `"One Way"` or `"Round Trip"` |
| `bookingUrl` | Link to verify/book | `"https://www.airindia.com"` |

---

## Tips

- **Update daily** at 9 AM
- **Remove old deals** weekly (just delete the `{ }` block)
- **Don't forget the comma** after each deal (except the last one)
- **Keep it real** - only post verified deals

---

## File Structure

```
/drops-simple.html      ← The page (edit deals here)
/DEALS.md               ← Reference only (optional)
/DROPS_SIMPLE_README.md ← This file
```

---

## Homepage Integration (Optional)

Want to add a preview to your homepage?

Add this anywhere in `index.html`:

```html
<section class="py-20 bg-gradient-to-b from-black to-gray-900">
    <div class="max-w-6xl mx-auto px-6 text-center">
        <h2 class="text-5xl font-bold text-white mb-6">
            FlyCharm Drops 🔥
        </h2>
        <p class="text-xl text-gray-400 mb-10">
            Insane flight deals updated daily
        </p>
        <a href="drops-simple.html" class="bg-lime-400 text-black px-8 py-4 rounded-full font-bold inline-block hover:scale-105 transition">
            See Live Deals
        </a>
    </div>
</section>
```

---

## Social Sharing Template

```
🔥 New Drop

Delhi → Dubai: ₹8,999
(Usually ₹18,500)

One Way • Dec 15

See all deals: flycharm.io/drops-simple.html
```

---

## That's It

No complex docs. No strategy PDFs. Just:
1. Edit the deals array
2. Save
3. Share

**Simple. Clean. Effective.**
