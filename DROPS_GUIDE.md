# FlyCharm Drops - Management Guide

## 🔥 What is FlyCharm Drops?

FlyCharm Drops is your real-time deal discovery engine that showcases insanely cheap flight prices. It's designed to:
- Drive daily repeat traffic
- Create viral "deal dopamine hits"
- Convert viewers into FlyCharm customers
- Build trust through transparency and value

---

## 📍 How to Update Deals (Simple & Fast)

All deals are managed directly in `drops.html`. No database, no complex setup - just edit the JavaScript array.

### Step 1: Open the File

Open `/drops.html` in any text editor.

### Step 2: Find the Data Section

Look for this section (around line 150-250):

```javascript
const dealsData = [
    {
        id: 1,
        from: "DEL",
        fromCity: "Delhi",
        to: "DXB",
        toCity: "Dubai",
        price: 8999,
        originalPrice: 18500,
        currency: "₹",
        airline: "Air India",
        departDate: "2025-12-15",
        returnDate: "2025-12-22",
        tripType: "Round Trip",
        validUntil: "2025-12-01",
        category: "international",
        originCity: "delhi",
        isHot: true,
        directBookingUrl: "https://www.airindia.com",
        whatsappMessage: "Hi! I saw the Delhi → Dubai deal (₹8,999) on FlyCharm Drops. Can you help me book this?"
    },
    // More deals...
];
```

### Step 3: Add or Edit Deals

**To ADD a new deal:**
1. Copy an existing deal object
2. Paste it at the end of the array (before the `];`)
3. Update all fields with new deal info
4. Make sure to increment the `id` number

**To EDIT an existing deal:**
1. Find the deal by searching for the route (e.g., "DEL" or "Delhi")
2. Update the fields you need to change
3. Save the file

**To REMOVE an expired deal:**
1. Delete the entire deal object (from `{` to `},`)
2. Save the file

---

## 📋 Deal Object Fields Explained

| Field | Type | Description | Example |
|-------|------|-------------|---------|
| `id` | Number | Unique identifier (increment for each deal) | `1` |
| `from` | String | 3-letter airport code (origin) | `"DEL"` |
| `fromCity` | String | Full city name (origin) | `"Delhi"` |
| `to` | String | 3-letter airport code (destination) | `"DXB"` |
| `toCity` | String | Full city name (destination) | `"Dubai"` |
| `price` | Number | Deal price (no commas, no currency symbol) | `8999` |
| `originalPrice` | Number | Regular price for comparison | `18500` |
| `currency` | String | Currency symbol | `"₹"` |
| `airline` | String | Airline name | `"Air India"` |
| `departDate` | String | Departure date (YYYY-MM-DD) | `"2025-12-15"` |
| `returnDate` | String | Return date (YYYY-MM-DD) or `null` for one-way | `"2025-12-22"` or `null` |
| `tripType` | String | Type of trip | `"Round Trip"` or `"One Way"` |
| `validUntil` | String | Deal expiry date (YYYY-MM-DD) - **IMPORTANT** | `"2025-12-01"` |
| `category` | String | Deal category | `"international"` or `"domestic"` |
| `originCity` | String | Origin city (lowercase, for filtering) | `"delhi"`, `"mumbai"`, or `"ahmedabad"` |
| `isHot` | Boolean | Show "Hot Deal" badge? | `true` or `false` |
| `directBookingUrl` | String | Link to airline/booking site | `"https://www.airindia.com"` |
| `whatsappMessage` | String | Pre-filled message for FlyCharm booking | `"Hi! I saw the Delhi → Dubai deal..."` |

---

## ⚡ Quick Tips

### Auto-Expiration
Deals automatically disappear after their `validUntil` date. The system checks this daily, so you don't need to manually remove old deals (but you can if you want to keep the file clean).

### Hot Deals
Set `isHot: true` for the best deals. These get a 🔥 badge and special styling.

### WhatsApp Messages
Keep these friendly and specific. Format:
```
"Hi! I saw the [Origin] → [Destination] deal (₹[Price]) on FlyCharm Drops. Can you help me book this?"
```

### Date Format
ALWAYS use `YYYY-MM-DD` format:
- ✅ `"2025-12-15"`
- ❌ `"12/15/2025"`
- ❌ `"15-12-2025"`

### City Names (originCity)
Must be lowercase and match one of:
- `"delhi"`
- `"mumbai"`
- `"ahmedabad"`

This is used for filtering.

---

## 🎯 Best Practices

### 1. **Update Daily**
Fresh deals = repeat visitors. Aim to add 1-3 new deals daily.

### 2. **Only the Craziest Deals**
If the savings aren't mind-blowing (40%+ off), don't add it. Quality > quantity.

### 3. **Mix International & Domestic**
Keep a balance:
- 2-3 international deals
- 2-3 domestic deals

### 4. **Target Cities**
Prioritize deals from:
- Delhi (DEL)
- Mumbai (BOM)
- Ahmedabad (AMD)

### 5. **Verify Prices**
Double-check that the deal is actually available. Nothing kills trust faster than fake deals.

### 6. **Expiry Dates**
Set `validUntil` dates realistically:
- Most deals: 3-7 days
- Flash deals: 1-2 days
- Extended deals: 7-14 days

---

## 📱 Testing Your Changes

After updating deals:

1. **Save the file**
2. **Refresh the page** (hard refresh: Ctrl+Shift+R or Cmd+Shift+R)
3. **Check:**
   - New deals appear correctly
   - Expired deals are hidden
   - Filters work (click city filters)
   - CTAs work (test WhatsApp and direct booking links)
   - Mobile display looks good

---

## 🔗 Important Links

**Live Drops Page:** https://flycharm.io/drops.html

**WhatsApp Number:** +919998156651

**Files to Edit:**
- Main drops page: `/drops.html`
- Homepage preview: `/index.html` (lines 846-980)

---

## 🚀 Growth Strategy

### Daily Routine
1. **9:00 AM IST:** Post new deals to Drops page
2. **9:15 AM:** Share top deal on Instagram Story
3. **9:30 AM:** Share in WhatsApp broadcast list (if you have one)
4. **Throughout day:** Monitor which deals get most clicks

### Social Amplification
Every deal can be shared. Use these templates:

**Instagram Story:**
```
🔥 INSANE DEAL ALERT

Delhi → Dubai
₹8,999 (51% off!)

Link in bio or DM "DROPS"
```

**WhatsApp Status:**
```
Found this insane deal 🔥

Delhi → Dubai
Round Trip: ₹8,999
(Usually ₹18,500!)

Check all deals: flycharm.io/drops
```

**Twitter/X:**
```
POV: You just found Delhi → Dubai flights for ₹8,999 (51% off) 🤯

Only at @FlyCharm Drops.
We post deals travel sites won't show you.

flycharm.io/drops
```

---

## 🎨 Customization (Optional)

### Homepage Preview
The homepage shows 2 featured deals. To update them:

1. Open `/index.html`
2. Find the "FLYCHARM DROPS PREVIEW" section (around line 846)
3. Update the deal cards with your latest hot deals
4. Keep it in sync with what's on drops.html

### Colors & Styling
All styling is in the `<style>` section of drops.html. Key colors:
- Lime (primary): `#D5FE00`
- Red (hot badge): `#FF3B3B`
- Orange (countdown): `#FF9500`
- Dark background: `#101010`

---

## ❓ FAQ

**Q: How many deals should I have live at once?**
A: 4-8 deals. Enough for variety, not so many it's overwhelming.

**Q: What if I don't have real deals to post?**
A: Don't post fake deals. Better to have 2 real deals than 10 fake ones. Trust is everything.

**Q: Can I automate this?**
A: Not yet. Manual curation ensures quality. You can explore Skyscanner API integration later.

**Q: How do I track which deals perform best?**
A: Add Google Analytics events or use a link shortener for the WhatsApp CTAs.

**Q: Should I remove expired deals or leave them?**
A: They auto-hide, but it's good to delete them every week to keep the file clean.

---

## 🆘 Troubleshooting

**Problem:** Deals not showing up
- **Check:** Is the `validUntil` date in the future?
- **Check:** Is the JavaScript syntax correct? (matching quotes, commas, brackets)

**Problem:** Filter not working
- **Check:** Is `originCity` lowercase? (`"delhi"` not `"Delhi"`)
- **Check:** Is `category` spelled correctly? (`"international"` or `"domestic"`)

**Problem:** WhatsApp link broken
- **Check:** Is the message URL-encoded properly?
- **Check:** Is the phone number correct? (+919998156651)

**Problem:** Page broken/white screen
- **Check:** JavaScript console for errors (F12 in browser)
- **Check:** Did you forget a comma between deals?
- **Check:** Are all quotes matching? (`"` not `'` unless consistent)

---

## 📊 Success Metrics to Track

- Daily page views on drops.html
- Click-through rate on "Book with FlyCharm" CTAs
- WhatsApp inquiries mentioning "Drops"
- Social shares per deal
- Repeat visitor rate
- Average time on page

---

## 💡 Ideas for V2 (Future)

- [ ] Skyscanner API integration for auto-population
- [ ] Email notification system
- [ ] Web push notifications
- [ ] Deal voting/favorites
- [ ] "Notify me" for specific routes
- [ ] Price drop alerts
- [ ] Historical "best deals" archive
- [ ] User-submitted deal requests

---

**Built with ❤️ by the FlyCharm team**

*Last updated: November 2025*
