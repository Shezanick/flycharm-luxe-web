# How to Update Deals - 30 Second Guide

## Step 1: Open the file

Open `drops-simple.html` in any text editor (VS Code, Sublime, even Notepad)

## Step 2: Find the deals section

Search for: `const deals = [`

You'll find this (around line 95):

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
    {
        route: "Mumbai → Singapore",
        price: "₹15,999",
        originalPrice: "₹35,000",
        date: "Dec 20-28",
        type: "Round Trip",
        bookingUrl: "https://www.singaporeair.com"
    }
    // ... more deals
];
```

## Step 3: Edit, add, or remove deals

### To EDIT a deal:
Just change the values:
```javascript
{
    route: "Delhi → Dubai",
    price: "₹6,999",  // Changed!
    originalPrice: "₹18,500",
    date: "Dec 20",    // Changed!
    type: "One Way",
    bookingUrl: "https://www.airindia.com"
},
```

### To ADD a new deal:
Copy this template and add it BEFORE the `];`:

```javascript
{
    route: "City → City",
    price: "₹0,000",
    originalPrice: "₹0,000",
    date: "Dec 15",
    type: "One Way",
    bookingUrl: "https://airline.com"
},
```

**Important:** Don't forget the comma at the end!

### To REMOVE a deal:
Just delete the entire `{ }` block (including the comma)

## Step 4: Save the file

Hit Save (Ctrl+S or Cmd+S)

## Step 5: Refresh the page

Open `drops-simple.html` in browser and refresh. Done!

---

## Quick Reference

**Field Guide:**
- `route` → "City → City" (use arrow: →)
- `price` → Deal price with ₹ symbol
- `originalPrice` → Regular price with ₹ symbol
- `date` → "Dec 15" OR "Dec 15-22" for round trip
- `type` → "One Way" OR "Round Trip"
- `bookingUrl` → Airline website link

**Example:**
```javascript
{
    route: "Ahmedabad → Bangkok",
    price: "₹12,499",
    originalPrice: "₹28,000",
    date: "Dec 10-17",
    type: "Round Trip",
    bookingUrl: "https://www.emirates.com"
},
```

---

## Common Mistakes

❌ **Forgot the comma:**
```javascript
{
    route: "Delhi → Dubai",
    price: "₹8,999"
    // Missing comma here!
}
{
    route: "Mumbai → Goa"  // This will break!
```

✅ **Correct:**
```javascript
{
    route: "Delhi → Dubai",
    price: "₹8,999"
},  // Comma here!
{
    route: "Mumbai → Goa"
```

❌ **Comma on last item:**
```javascript
{
    route: "Last deal",
    price: "₹5,000"
},  // Remove this comma - it's the last item!
];
```

✅ **Correct:**
```javascript
{
    route: "Last deal",
    price: "₹5,000"
}  // No comma on last item
];
```

---

## That's it!

Edit → Save → Refresh

**No database. No build process. No complexity.**

Just clean, simple deal management.
