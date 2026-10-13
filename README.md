# View Digital Printing — Android APK

`www/index.html` ကို Android App (APK) အဖြစ် GitHub Actions ကနေ အလိုအလျောက် build လုပ်ပေးမည့် project ဖြစ်သည်။
(Capacitor သုံးထားသည် — Android Studio မလိုပါ)

## APK ရယူနည်း

1. GitHub မှာ Repository အသစ်ဆောက်ပါ (ဥပမာ `view-digital-printing`)
2. ဒီ folder ထဲက ဖိုင်အားလုံး (`.github` folder အပါအဝင်) ကို Repository ထဲ Upload / push လုပ်ပါ
3. GitHub → **Actions** tab → **Build Android APK** က အလိုအလျောက် run မည် (မ run ရင် **Run workflow** နှိပ်ပါ)
4. ၃–၅ မိနစ်ခန့်နောက် Run ထဲဝင် → အောက်ဆုံး **Artifacts** မှာ `ViewDigitalPrinting-apk` ကို Download လုပ်ပါ (zip ဖြေရင် `ViewDigitalPrinting.apk`)
5. Android ဖုန်းမှာ APK ဖွင့်ပြီး Install လုပ်ပါ (_"မသိသော အရင်းအမြစ်မှ install" ခွင့်ပြုရန်_ လိုနိုင်သည်)

Release အဖြစ်ထုတ်ချင်ရင် Tag တင်ပါ — `git tag v1.0.0 && git push --tags` → **Releases** မှာ APK ပါလာမည်။

## App ကို ပြင်ချင်ရင်

- `www/index.html` ကိုပြင်ပြီး push လုပ်ရုံနဲ့ APK အသစ် ပြန် build ဖြစ်သည်
- **Customer APK မှာ Cloud အလိုအလျောက်ချိတ်ချင်ရင်** `www/index.html` ထဲက
  `const DEFAULT_CLOUD="";` မှာ URL ထည့်ပါ (ဥပမာ `const DEFAULT_CLOUD="https://xxxx-default-rtdb.firebaseio.com";`)
  — Customer က Link / URL ထပ်ထည့်စရာမလိုတော့ပါ
- App အမည်/Package ID ပြောင်းချင်ရင် `capacitor.config.json` (`appName`, `appId`)
- App icon ပြောင်းချင်ရင် `assets/icon-only.png`, `icon-foreground.png`, `icon-background.png` (1024×1024) ကို အစားထိုးပါ

## သတိပြုရန်

- ထွက်လာတာက **Debug APK** ဖြစ်ပြီး ကိုယ်တိုင်ဖြန့်ဝေ/Install လုပ်ဖို့ လုံလောက်သည်။ Google Play တင်ချင်ရင် Signed Release (AAB) သီးသန့်လိုသည်။
- 💾 **Backup (ဖိုင်ဒေါင်းလုတ်)** ခလုတ်က APK ထဲမှာ အလုပ်မလုပ်နိုင်ပါ (WebView ကန့်သတ်ချက်)။ Backup ကို Cloud Sync ဖြင့်ပဲ အားကိုးပါ။
- ပထမဆုံး 🎤 အသံပို့တဲ့အခါ Microphone ခွင့်ပြုချက် မေးမည်။
- Offline မုဒ်ရဲ့ ဒေတာတွေက ဖုန်းထဲမှာပဲ သိမ်းထားသည် — App ကို Uninstall လုပ်ရင် ပျက်မည်။
