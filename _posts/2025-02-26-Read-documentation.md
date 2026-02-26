# When Your AI Fails You

As a software developer, I'm 99% sure every one of us has tried debugging code with AI at some point. For simple tasks and isolated issues, it's generally reliable. With AI baked into IDEs like Cursor or Claude Code, you can usually pinpoint the core issue in your project pretty quickly.

But what if your project spans multiple packages, frameworks, and environments? What if the issue lives *outside* your own code and you need a more macroscopic point of view?

## This is why we can't forget the OG debugging method - researching one by one

Recently, I've been shifting more into mobile app development after spending my first couple of years as a frontend developer. Because I wasn't fully in tune with the mobile development ecosystem, I was struggling to push an updated app to the Google Play Store.

The culprit? The **16 KB page size** requirement that Google Play introduced. Starting November 1, 2025, all app updates targeting Android 15+ must support 16 KB memory page sizes, and our app was getting blocked because of it.

My senior did some AI-assisted searching and Googling, and decided we should upgrade from Expo SDK 53 to SDK 54 - he believed that would sort things out, and so did I.

But it didn't. The issue persisted and we still couldn't ship the update.

This task eventually landed on me, and I'll be honest - I was quietly blaming my senior for throwing me into mobile territory when I was still finding my footing. But I don't feel that way anymore. I'm actually grateful he threw me into the deep end.

So, like my senior before me, I turned to my AI agent for help. And it was no use at all. It kept suggesting I tweak `app.config` and build files, which had nothing to do with the actual problem. (I was using one of the smartest AI tools on the market, just so you know.)

After half a day of bouncing between different AI tools and getting nowhere, I realized I needed to go back to basics.

### Reading documentation and dev blogs

I went back to the original error: `Not supporting 16 KB page size`. There was [official Android documentation](https://developer.android.com/guide/practices/page-sizes) on the issue and how to diagnose it. The docs laid out several debugging approaches, and working through them led me to this [Android Developers blog post](https://android-developers.googleblog.com/2025/05/prepare-play-apps-for-devices-with-16kb-page-size.html) - which explained exactly how to identify which packages inside your app bundle aren't compatible with the new page size requirement.

Checking the memory page alignment from the app bundle finally gave me clarity: I could see *exactly* which packages were the problem.

### Scavenging GitHub issue threads

The culprits turned out to be `react-native-mmkv` and `react-native-pdf`. The next step was heading to their GitHub issue pages and reading through what other developers had already been through.

It didn't take long to find several viable solutions - either upgrading to a beta version of the package or patching the node module manually.

---

Even though this whole debugging journey felt like finding a needle in a haystack, it was a good reminder that reading official documentation, digging through developer blogs, and sifting through GitHub issues is still an essential skill - especially when the problem is bigger than your own codebase.

AI is a great co-pilot. But sometimes you've got to take the wheel yourself.
