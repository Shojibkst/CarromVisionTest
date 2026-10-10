# Carrom Vision Test — GitHub-এ APK তৈরি

এটি একটি প্রাথমিক Android/Kotlin প্রোটোটাইপ। এতে আলাদা প্রিভিউ স্ক্রিনে নমুনা রেখা আঁকা এবং Android-এর MediaProjection অনুমতি-ডায়ালগ পরীক্ষা করা যায়।

## গুরুত্বপূর্ণ সীমাবদ্ধতা
- এই সংস্করণ আসলে স্ক্রিন ফ্রেম ক্যাপচার বা সংরক্ষণ করে না।
- OpenCV/AI দিয়ে গুটি শনাক্তকরণ এখনো যুক্ত নয়।
- অন্য অ্যাপের ওপর overlay বা গেমের অটোমেশন নেই।
- পরের ধাপে MediaProjection foreground service ও অনুমোদিত Computer Vision প্রক্রিয়া যোগ করতে হবে।

## GitHub থেকে APK তৈরি
1. GitHub-এ `CarromVisionTest` নামে একটি repository তৈরি করুন।
2. এই ZIP-এর ভেতরের সব ফাইল ও ফোল্ডার repository-র root-এ আপলোড করুন। `.github/workflows/build-apk.yml` ফাইলটিও রাখতে হবে।
3. `Settings` থেকে নিশ্চিত করুন Actions নিষ্ক্রিয় করা নেই।
4. `Actions` ট্যাবে যান এবং `Build Carrom Vision Test APK` workflow খুলুন।
5. `Run workflow` চাপুন। বিল্ড শেষ হলে workflow run-এর পৃষ্ঠার `Artifacts` অংশ থেকে `CarromVisionTest-debug-apk` ডাউনলোড করুন।
6. ZIP artifact খুলে `app-debug.apk` বের করে নিজের ফোনে ইনস্টল করুন। Android প্রয়োজনে ব্রাউজার/ফাইল ম্যানেজারের জন্য install permission চাইবে।

## প্রজেক্টের প্রধান ফাইল
- `app/src/main/java/com/example/carromvisiontest/MainActivity.kt`
- `app/src/main/AndroidManifest.xml`
- `app/build.gradle.kts`
- `.github/workflows/build-apk.yml`

এই workflow একটি **debug APK** তৈরি করে; এটি Play Store প্রকাশনার জন্য signed release build নয়।
