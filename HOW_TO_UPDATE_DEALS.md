# How to Update Deals - Premium Edition 🔥

## Step 1: Open the file

Open `drops-simple.html` in any text editor

## Step 2: Find the deals section

Search for: `const deals = [`

You'll find this (around line 229):

```javascript
const deals = [
    {
        from: "Delhi",
        route: "Delhi → Dubai",
        price: "₹8,999",
        originalPrice: "₹18,500",
        date: "Dec 15",
        type: "One Way",
        cabin: "Economy",
        image: "https://images.unsplash.com/photo-1512453979798-5ea266f8880c?w=800&h=600&fit=crop",
        bookingUrl: "https://www.airindia.com"
    },
    // ... more deals
];
```

## Step 3: Add/Edit/Remove deals

### To ADD a new deal:

Copy this template:

```javascript
{
    from: "Delhi",  // Departure city (for filtering)
    route: "Delhi → London",
    price: "₹32,999",
    originalPrice: "₹68,000",
    date: "Dec 15-22",  // Single date OR range
    type: "Round Trip",  // "One Way" or "Round Trip"
    cabin: "Business",  // "Economy" or "Business"
    image: "https://images.unsplash.com/photo-1513635269975-59663e0ac1ad?w=800&h=600&fit=crop",
    bookingUrl: "https://www.britishairways.com"
},
```

**Important:** Don't forget the comma at the end!

### To EDIT a deal:

Just change the values you need.

### To REMOVE a deal:

Delete the entire `{ }` block (including the comma).

---

## Field Guide (All 9 Fields Explained)

| Field | What It Is | Examples | Notes |
|-------|-----------|----------|-------|
| `from` | Departure city | `"Delhi"`, `"Mumbai"`, `"Ahmedabad"` | **Must** match exactly (case-sensitive) for filters to work |
| `route` | Full route display | `"Delhi → Dubai"` | Use arrow symbol: → |
| `price` | Deal price | `"₹8,999"` | Include ₹ symbol |
| `originalPrice` | Regular price | `"₹18,500"` | Include ₹ symbol |
| `date` | Travel date(s) | `"Dec 15"` or `"Dec 15-22"` | Single date for one-way, range for round trip |
| `type` | Trip type | `"One Way"` or `"Round Trip"` | Exactly these values |
| `cabin` | Class of service | `"Economy"` or `"Business"` | Exactly these values (changes badge color) |
| `image` | Destination photo | See below | Use Unsplash URLs |
| `bookingUrl` | Airline/booking link | `"https://www.airindia.com"` | Full URL |

---

## How to Find Great Images (Unsplash)

**Formula:**
```
https://images.unsplash.com/photo-[PHOTO_ID]?w=800&h=600&fit=crop
```

**Quick Image Search:**
1. Go to https://unsplash.com
2. Search for destination (e.g., "Dubai skyline")
3. Click a photo
4. Copy the photo ID from URL
5. Use format above

**Example Popular Destinations:**

```javascript
// Dubai
image: "https://images.unsplash.com/photo-1512453979798-5ea266f8880c?w=800&h=600&fit=crop"

// Singapore
image: "https://images.unsplash.com/photo-1525625293386-3f8f99389edd?w=800&h=600&fit=crop"

// London
image: "https://images.unsplash.com/photo-1513635269975-59663e0ac1ad?w=800&h=600&fit=crop"

// Bangkok
image: "https://images.unsplash.com/photo-1508009603885-50cf7c579365?w=800&h=600&fit=crop"

// Goa beach
image: "https://images.unsplash.com/photo-1571847248879-7a85a6db9f2f?w=800&h=600&fit=crop"

// Paris
image: "https://images.unsplash.com/photo-1502602898657-3e91760cbb34?w=800&h=600&fit=crop"

// New York
image: "https://images.unsplash.com/photo-1496442226666-8d4d0e62e6e9?w=800&h=600&fit=crop"

// Tokyo
image: "https://images.unsplash.com/photo-1540959733332-eab4deabeeaf?w=800&h=600&fit=crop"

// Bali
image: "https://images.unsplash.com/photo-1537996194471-e657df975ab4?w=800&h=600&fit=crop"
```

---

## City Filter Requirements

**CRITICAL:** The `from` field MUST match EXACTLY for filters to work:

✅ **Correct:**
```javascript
from: "Delhi",    // Matches "Delhi" filter
from: "Mumbai",   // Matches "Mumbai" filter
from: "Ahmedabad" // Matches "Ahmedabad" filter
```

❌ **Wrong:**
```javascript
from: "delhi",      // Won't match (lowercase)
from: "DEL",        // Won't match (airport code)
from: "New Delhi",  // Won't match (different name)
```

---

## Cabin Class Badge Colors

**Economy:**
- Gray badge
- Subtle styling
- Most deals should be Economy

**Business:**
- Lime/green badge (matches brand)
- Premium feel
- Use for actual business class deals

```javascript
cabin: "Economy"   // → Gray badge
cabin: "Business"  // → Lime badge
```

---

## Complete Example Deal

```javascript
{
    from: "Mumbai",
    route: "Mumbai → Singapore",
    price: "₹15,999",
    originalPrice: "₹35,000",
    date: "Dec 20-28",
    type: "Round Trip",
    cabin: "Economy",
    image: "https://images.unsplash.com/photo-1525625293386-3f8f99389edd?w=800&h=600&fit=crop",
    bookingUrl: "https://www.singaporeair.com"
},
```

This will show:
- In Mumbai filter (because `from: "Mumbai"`)
- Economy badge (gray)
- Singapore skyline image
- ₹15,999 price with 54% savings badge
- Round trip label
- Dec 20-28 dates

---

## Common Mistakes

### ❌ Forgot comma

```javascript
{
    from: "Delhi",
    route: "Delhi → Dubai",
    price: "₹8,999"
    // Missing comma!
}
{
    from: "Mumbai"  // This will break!
```

✅ **Fix:** Add comma
```javascript
{
    from: "Delhi",
    route: "Delhi → Dubai",
    price: "₹8,999"
},  // ← Comma here!
{
    from: "Mumbai"
```

---

### ❌ Wrong city name

```javascript
from: "delhi",  // Lowercase won't match filter
```

✅ **Fix:** Use exact match
```javascript
from: "Delhi",  // Exactly "Delhi", "Mumbai", or "Ahmedabad"
```

---

### ❌ Wrong cabin value

```javascript
cabin: "economy",    // Lowercase won't work
cabin: "First Class" // Not supported
```

✅ **Fix:** Use exact values
```javascript
cabin: "Economy"   // or "Business" (capital E, capital B)
```

---

### ❌ Comma on last item

```javascript
{
    from: "Delhi",
    route: "Delhi → London",
    price: "₹32,999"
},  // ← Remove this comma! (it's the last item)
];
```

✅ **Fix:** No comma on last
```javascript
{
    from: "Delhi",
    route: "Delhi → London",
    price: "₹32,999"
}  // ← No comma
];
```

---

## Pro Tips

1. **Always use real images of the destination** - Makes deals 10x more clickable
2. **Economy for most deals** - Only use Business if it's actually business class
3. **Keep city names consistent** - Always "Delhi", "Mumbai", "Ahmedabad" (no variations)
4. **Test filters after adding deals** - Click Delhi/Mumbai/Ahmedabad to verify
5. **Use round numbers for prices** - ₹8,999 reads better than ₹8,973

---

## Testing Your Changes

After editing:

1. **Save the file** (Ctrl+S or Cmd+S)
2. **Refresh browser** (Ctrl+Shift+R or Cmd+Shift+R for hard refresh)
3. **Test city filters** - Click each city button
4. **Check images** - Make sure they load
5. **Test CTAs** - Click "Book with FlyCharm" (opens WhatsApp)
6. **Mobile test** - View on phone to check responsive design

---

## Quick Reference Card

**3 Required Cities:**
- `"Delhi"`
- `"Mumbai"`
- `"Ahmedabad"`

**2 Trip Types:**
- `"One Way"`
- `"Round Trip"`

**2 Cabin Classes:**
- `"Economy"` (gray badge)
- `"Business"` (lime badge)

**Image Format:**
```
https://images.unsplash.com/photo-[ID]?w=800&h=600&fit=crop
```

**Date Formats:**
- One Way: `"Dec 15"`
- Round Trip: `"Dec 15-22"`

---

## That's It!

**Edit → Save → Refresh → Test Filters → Done**

Premium flight deals with gorgeous images, sorted by city, with Economy/Business class badges.

**Stupidly good, just like the deals.** 🔥
