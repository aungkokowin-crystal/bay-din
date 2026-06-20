# 🔒 Owner-only data collection — Supabase Setup (၄ ဆင့်)

သူငယ်ချင်းတွေ အဖြေ + data အားလုံးကို **သင် တစ်ယောက်တည်း** Supabase မှာ ကြည့်နိုင်အောင်။

## ၁. Table + Security ဆောက်
- Supabase Dashboard ဖွင့် → ကိုယ့် project ရွေး
- ဘယ်ဘက် menu က **SQL Editor** → **New query**
- `supabase-setup.sql` ထဲက SQL အကုန် ကူးထည့် → **RUN** နှိပ်
- ✅ `predictions` table + RLS policy ဆောက်ပြီးသွားမယ်

## ၂. URL + anon key ယူ
- ဘယ်ဘက် menu အောက်ဆုံး **Project Settings (⚙️) → Data API**
- **Project URL** ကို copy (ဥပမာ `https://abcd1234.supabase.co`)
- **Project API keys** ထဲက **`anon` `public`** key ကို copy
  - 🔒 ဒီ anon key က public ဖြစ်လည်း လုံခြုံ — RLS ကြောင့် INSERT ပဲ ရတယ်၊ data ဖတ်လို့မရ

## ၃. index.html ထဲ ထည့်
`index.html` ထဲ ရှာ:
```js
const SUPABASE_URL      = "";
const SUPABASE_ANON_KEY = "";
```
copy ထားတာတွေ ထည့်:
```js
const SUPABASE_URL      = "https://abcd1234.supabase.co";
const SUPABASE_ANON_KEY = "eyJhbGciOi....(anon key)";
```

## ၄. Netlify မှာ ပြန်တင်
- folder ကို [app.netlify.com/drop](https://app.netlify.com/drop) ထဲ ထပ်ဆွဲချ → live!

---

## ✅ ပြီးရင် —
- သူငယ်ချင်းတွေ link နဲ့ တွက်တိုင်း → Supabase `predictions` table ထဲ row တိုးလာမယ်
- **data ကြည့်ဖို့:** Dashboard → **Table Editor → predictions**
- 🔒 သင် login လုပ်မှ မြင်ရတယ်။ သူငယ်ချင်းတွေ link ထဲက anon key နဲ့ **ဖတ်လို့ မရဘူး** (INSERT only)
- ဖြေသူက ကိုယ့်ဖုန်းမှာ ကိုယ့်အဖြေ (history) ပဲ မြင်ရတယ်

## ⚠️ စစ်ဆေးရန်
setup ပြီးရင် app မှာ ဟောစာတမ်း တစ်ခါတွက်ကြည့် → Supabase Table Editor မှာ row ဝင်မဝင် စစ်ပါ။
row မဝင်ရင် — URL/anon key မှန်မမှန်၊ SQL RUN ပြီးပြီလား ပြန်စစ်ပါ။
