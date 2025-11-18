# How to Update Deals - JSON Edition 🚀

## ✨ New System: Edit One File, Update Everything

All deals are now in **`deals.json`** - edit this file daily at 9 PM IST.

---

## 📝 Quick Start (30 Seconds)

1. Open `deals.json`
2. Edit the deals
3. Save
4. Refresh the website
5. Done ✅

---

## 📋 Deal Template (Copy & Paste)

```json
{
    "from": "Mumbai",
    "route": "Mumbai → Paris",
    "destination": "France",
    "price": "₹45,000",
    "originalPrice": "₹95,000",
    "travelDates": "15 Mar - 22 Mar 2026",
    "departDate": "15 Mar 2026",
    "returnDate": "22 Mar 2026",
    "stops": "1 stop",
    "cabin": "Economy",
    "image": "https://images.unsplash.com/photo-1502602898657-3e91760cbb34?w=800&h=600&fit=crop",
    "bookingUrl": "https://www.skyscanner.co.in"
}
```

**Important:** Don't forget the comma after `}` unless it's the last deal!

---

## 🎯 Field Guide

| Field | What It Is | Example |
|-------|-----------|---------|
| `from` | Departure city (for filters) | `"Mumbai"`, `"Delhi"`, `"Bengaluru"` |
| `route` | Full route with arrow | `"Mumbai → Paris"` |
| `destination` | Country/region name | `"France"`, `"United States"`, `"Thailand"` |
| `price` | Deal price with ₹ | `"₹45,000"` |
| `originalPrice` | Regular price with ₹ | `"₹95,000"` |
| `travelDates` | Display dates | `"15 Mar - 22 Mar 2026"` |
| `departDate` | Departure date | `"15 Mar 2026"` |
| `returnDate` | Return date | `"22 Mar 2026"` |
| `stops` | Flight type | `"Non stop"` or `"1 stop"` or `"2 stops"` |
| `cabin` | Class of service | `"Economy"` or `"Business"` |
| `image` | Unsplash photo URL | See image guide below |
| `bookingUrl` | Where to book | `"https://www.skyscanner.co.in"` |

---

## 📅 Date Formatting (CRITICAL)

**Display Format** (`travelDates`):
- Round trip: `"15 Jan - 22 Jan 2026"`
- One way: `"15 Jan 2026"`

**Individual Dates** (`departDate`, `returnDate`):
- Always: `"15 Jan 2026"`
- Format: `"DD MMM YYYY"`

**Examples:**
```json
"travelDates": "10 Feb - 24 Feb 2026",
"departDate": "10 Feb 2026",
"returnDate": "24 Feb 2026"
```

---

## 🌍 Finding Images (Unsplash)

**Quick Image Library:**

```json
// Paris
"image": "https://images.unsplash.com/photo-1502602898657-3e91760cbb34?w=800&h=600&fit=crop"

// Dubai
"image": "https://images.unsplash.com/photo-1512453979798-5ea266f8880c?w=800&h=600&fit=crop"

// London
"image": "https://images.unsplash.com/photo-1513635269975-59663e0ac1ad?w=800&h=600&fit=crop"

// New York
"image": "https://images.unsplash.com/photo-1496442226666-8d4d0e62e6e9?w=800&h=600&fit=crop"

// Bangkok
"image": "https://images.unsplash.com/photo-1508009603885-50cf7c579365?w=800&h=600&fit=crop"

// Singapore
"image": "https://images.unsplash.com/photo-1525625293386-3f8f99389edd?w=800&h=600&fit=crop"

// Tokyo
"image": "https://images.unsplash.com/photo-1540959733332-eab4deabeeaf?w=800&h=600&fit=crop"

// Bali
"image": "https://images.unsplash.com/photo-1537996194471-e657df975ab4?w=800&h=600&fit=crop"
```

**To find new images:**
1. Go to https://unsplash.com
2. Search for destination (e.g., "Athens Parthenon")
3. Click photo → Copy photo ID from URL
4. Use format: `https://images.unsplash.com/photo-[ID]?w=800&h=600&fit=crop`

---

## 🏙️ City Filter Names (Must Match Exactly)

Your `from` field **must** match one of these exactly:
- `"Delhi"`
- `"Mumbai"`
- `"Ahmedabad"`
- `"Bengaluru"`
- `"Chennai"`
- `"Hyderabad"`
- `"Kolkata"`
- `"Kochi"`

**Case-sensitive!** Use capital first letter.

---

## ✈️ Adding a New Deal

Open `deals.json` and add your deal **before** the last `]`:

```json
[
    {
        "from": "Mumbai",
        "route": "Mumbai → Athens",
        ...existing deal...
    },
    {
        "from": "Delhi",
        "route": "New Delhi → Paris",
        "destination": "France",
        "price": "₹48,500",
        "originalPrice": "₹98,000",
        "travelDates": "20 Mar - 30 Mar 2026",
        "departDate": "20 Mar 2026",
        "returnDate": "30 Mar 2026",
        "stops": "1 stop",
        "cabin": "Economy",
        "image": "https://images.unsplash.com/photo-1502602898657-3e91760cbb34?w=800&h=600&fit=crop",
        "bookingUrl": "https://www.skyscanner.co.in"
    }
]
```

**Don't forget the comma** after the previous deal's `}`!

---

## ❌ Removing a Deal

Just delete the entire `{ }` block:

```json
[
    {
        ...keep this deal...
    },
    {
        ...DELETE THIS ENTIRE BLOCK...
    },  ← Don't forget to remove this comma too if it's now the last deal!
    {
        ...keep this deal...
    }
]
```

---

## 🎨 What Shows on the Card

When you add a deal, here's what users see:

```
┌──────────────────────────────┐
│ [Beautiful Photo]            │
│         [Economy Badge] ──┐  │
│                           │  │
├──────────────────────────────┤
│ GREECE ← Destination          │
│ Athens ← City name           │
│                              │
│ 📅 15 Mar - 22 Mar 2026      │
│                              │
│ 1 stop • From Mumbai         │
│                              │
│ ₹45,000  [Save 53%]          │
│ ₹95,000                      │
│                              │
│ [Book with FlyCharm]         │
│ or book direct →             │
└──────────────────────────────┘
```

---

## 💬 WhatsApp Message Format

When users click "Book with FlyCharm", they get this message:

```
Hi! I saw the Mumbai → Paris Economy deal (₹45,000) on FlyCharm Drops.

Dates: 15 Mar - 22 Mar 2026
1 stop

Can you help me book this?
```

**All data pulled automatically from the JSON!**

---

## ⚡ Pro Tips

1. **Update at 9 PM IST daily** - Consistency builds habit
2. **Use specific dates** - "15 Jan 2026" not "Jan 2026"
3. **Real photos only** - Iconic landmarks work best
4. **Keep 10-15 deals live** - Enough variety, not overwhelming
5. **Mix origins** - Balance Delhi, Mumbai, Bengaluru, etc.
6. **Economy > Business** - Most deals should be Economy
7. **Verify prices** - Don't post fake deals, trust is everything

---

## 🧪 Testing Your Changes

After editing `deals.json`:

1. **Save the file** (Ctrl+S or Cmd+S)
2. **Open/refresh** drops-simple.html in browser
3. **Check loading** - Should show 3 skeleton cards briefly
4. **Verify deals appear** - All your deals should render
5. **Test filters** - Click each city filter
6. **Test CTA** - Click "Book with FlyCharm" to check WhatsApp message
7. **Mobile test** - Check on phone

---

## 🐛 Common Mistakes

### ❌ Missing comma
```json
{
    "from": "Delhi",
    "price": "₹50,000"
}  ← Need comma here!
{
    "from": "Mumbai"
```

### ✅ Fixed
```json
{
    "from": "Delhi",
    "price": "₹50,000"
},  ← Comma added!
{
    "from": "Mumbai"
```

---

### ❌ Wrong date format
```json
"travelDates": "15/03/2026"  ← Wrong!
"departDate": "March 15, 2026"  ← Wrong!
```

### ✅ Fixed
```json
"travelDates": "15 Mar - 22 Mar 2026"  ← Correct!
"departDate": "15 Mar 2026"  ← Correct!
```

---

### ❌ Wrong city name
```json
"from": "delhi"  ← Lowercase won't work!
"from": "New Delhi"  ← Too specific!
```

### ✅ Fixed
```json
"from": "Delhi"  ← Perfect!
```

---

## 🚀 Daily Workflow

**Every day at 9 PM:**

1. Open `deals.json`
2. Remove expired deals (old travel dates)
3. Add 2-3 new deals
4. Save file
5. Deploy/push to website
6. Post to social media

**Time needed:** 10-15 minutes

---

## 📊 JSON File Structure

```json
[
    {
        ...deal 1...
    },
    {
        ...deal 2...
    },
    {
        ...deal 3...
    }
]
```

- Starts with `[`
- Ends with `]`
- Each deal wrapped in `{ }`
- Commas between deals
- No comma after last deal

---

## ✨ That's It!

**One file. One format. Infinite deals.**

Edit `deals.json` → Save → Refresh → Done.

No HTML. No JavaScript. Just clean JSON data.

**Stupidly simple. Just like the deals.** 🔥

---

**Questions?** Check `deals.json` for examples of all 15 current deals.
