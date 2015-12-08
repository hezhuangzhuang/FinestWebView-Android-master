# FinestWebView
[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-FinestWebView-brightgreen.svg?style=flat)](https://android-arsenal.com/details/1/2861)
[![Platform](https://img.shields.io/badge/platform-android-green.svg)](http://developer.android.com/index.html)
[![API](https://img.shields.io/badge/API-7%2B-brightgreen.svg?style=flat)](https://android-arsenal.com/api?level=7)
[![License](https://img.shields.io/badge/License-MIT-blue.svg?style=flat)](http://opensource.org/licenses/MIT)

#### Beautiful and customizable Android Activity that shows web pages within an app.

* Builder pattern
* Material design & Pre-made icons
* Custom themes & Custom transition animations
* Support collapsing toolbar & contextual actionbar
* SwipeRefreshLayout & Progressbar
* Device rotation
* Gradient divider
* Custom typeface

## Screenshots
<img src="https://github.com/TheFinestArtist/FinestWebView-Android/blob/master/art/screenshots.png?raw=true" width="888">

### Default theme & Copied to clipboard
<img src="https://github.com/TheFinestArtist/FinestWebView-Android/blob/master/art/first.png?raw=true" width="888">

### Back and forward & More options
<img src="https://github.com/TheFinestArtist/FinestWebView-Android/blob/master/art/second.png?raw=true" width="888">

## FinestWebView Demo Video - YouTube
<a href="https://www.youtube.com/watch?v=7qmAqnspjAM" target="_blank">
  <img alt="Youtube"
       src="https://github.com/TheFinestArtist/FinestWebView-Android/blob/master/art/youtube.png">
</a>


## Sample Project

You can download the latest sample APK from this repo here: [sample-release.apk](https://github.com/TheFinestArtist/FinestWebView-Android/blob/master/sample/sample-release.apk?raw=true)

It's also on Google Play:

<a href="https://play.google.com/store/apps/details?id=com.thefinestartist.finestwebview.sample" target="_blank">
  <img alt="Get it on Google Play"
       src="https://developer.android.com/images/brand/en_generic_rgb_wo_60.png" />
</a>

## Getting started

#### Gradle Dependency (jcenter)

Easily reference the library in your Android projects using this dependency in your module's `build.gradle` file.

```java
dependencies {
    compile 'com.thefinestartist:finestwebview:1.0.6'
}
```

#### Manifest Settings

FinestWebView is basically and Android activity with webview, toolbar and etc.  
You have to add FinestWebViewActivity in your `AndroidManifest.xml`

```xml
<uses-permission android:name="android.permission.INTERNET" />

<activity
    android:name="com.thefinestartist.finestwebview.FinestWebViewActivity"
    android:configChanges="keyboardHidden|orientation|screenSize"
    android:screenOrientation="sensor"
    android:theme="@style/FinestWebViewTheme.Light" />
```

#### Basic WebView

```java
new FinestWebView.Builder(activity).show(url);
```


## Customization

#### There are 2 ways to customize FinestWebView.

### 1. Using Themes

You can use your own Theme for FinestWebView. If you want to use pre-defined theme, use `android:theme="@style/FinestWebViewTheme"` or `android:theme="@style/FinestWebViewTheme.Fullscreen"`

```xml
<style name="AppTheme.NoActionBar" parent="Theme.AppCompat.Light.NoActionBar">
    <item name="colorPrimary">@color/primary</item>
    <item name="colorPrimaryDark">@color/primary_dark</item>
    <item name="colorAccent">@color/accent</item>
    <item name="android:textColorPrimary">@color/primary_text</item>
    <item name="android:textColorSecondary">@color/secondary_text</item>
    <item name="windowActionModeOverlay">true</item>
</style>
```

```xml
<activity
    android:name="com.thefinestartist.finestwebview.FinestWebViewActivity"
    android:theme="@style/AppTheme.NoActionBar" />
```

### 2. Builder Options

**Theme Options**
```java
theme(@StyleRes int theme);
```

**StatusBar Options**
```java
statusBarColor(@ColorInt int color);
statusBarColorRes(@ColorRes int color);
```

**Toolbar Options**
```java
toolbarColor(@ColorInt int color);
toolbarColorRes(@ColorRes int color);
toolbarScrollFlags(@ScrollFlags int flags);
```

**Icon Options**
```java
iconDefaultColor(@ColorInt int color);
iconDefaultColorRes(@ColorRes int color);
iconDisabledColor(@ColorInt int color);
iconDisabledColorRes(@ColorRes int colorRes);
iconPressedColor(@ColorInt int color);
iconPressedColorRes(@ColorRes int colorRes);
iconSelector(@DrawableRes int selectorRes);
```

**SwipeRefreshLayout Options**
```java
showSwipeRefreshLayout(boolean showSwipeRefreshLayout);
swipeRefreshColor(@ColorInt int color);
swipeRefreshColorRes(@ColorRes int colorRes);
swipeRefreshColors(int[] colors);
swipeRefreshColorsRes(@ArrayRes int colorsRes);
```

**Divider Options**
```java
showDivider(boolean showDivider);
gradientDivider(boolean gradientDivider);
dividerColor(@ColorInt int color);
dividerColorRes(@ColorRes int colorRes);
dividerHeight(float height);
dividerHeight(int height);
dividerHeightRes(@DimenRes int height);
```

**ProgressBar Options**
```java
showProgressBar(boolean showProgressBar);
progressBarColor(@ColorInt int color);
progressBarColorRes(@ColorRes int colorRes);
progressBarHeight(float height);
progressBarHeight(int height);
progressBarHeightRes(@DimenRes int height);
progressBarPosition(@NonNull Position position);
```

**Title Options**
```java
titleDefault(@NonNull String title);
titleDefaultRes(@StringRes int stringRes);
updateTitleFromHtml(boolean updateTitleFromHtml);
titleSize(float titleSize);
titleSize(int titleSize);
titleSizeRes(@DimenRes int titleSize);
titleFont(String titleFont);
titleColor(@ColorInt int color);
titleColorRes(@ColorRes int colorRes);
```

**Url Options**
```java
showUrl(boolean showUrl);
urlSize(float urlSize);
urlSize(int urlSize);
urlSizeRes(@DimenRes int urlSize);
urlFont(String urlFont);
urlColor(@ColorInt int color);
urlColorRes(@ColorRes int colorRes);
```

**Menu Options**
```java
menuColor(@ColorInt int color);
menuColorRes(@ColorRes int colorRes);
menuDropShadowColor(@ColorInt int color);
menuDropShadowColorRes(@ColorRes int colorRes);
menuDropShadowSize(float menuDropShadowSize);
menuDropShadowSize(int menuDropShadowSize);
menuDropShadowSizeRes(@DimenRes int menuDropShadowSize);
menuSelector(@DrawableRes int selectorRes);

menuTextSize(float menuTextSize);
menuTextSize(int menuTextSize);
menuTextSizeRes(@DimenRes int menuTextSize);
menuTextFont(String menuTextFont);
menuTextColor(@ColorInt int color);
menuTextColorRes(@ColorRes int colorRes);

showMenuRefresh(boolean showMenuRefresh);
stringResRefresh(@StringRes int stringResRefresh);
showMenuShareVia(boolean showMenuShareVia);
stringResShareVia(@StringRes int stringResShareVia);
showMenuCopyLink(boolean showMenuCopyLink);
stringResCopyLink(@StringRes int stringResCopyLink);
showMenuOpenWith(boolean showMenuOpenWith);
stringResOpenWith(@StringRes int stringResOpenWith);
```

**More Options**
```java
setCustomAnimations(@AnimRes int animationOpenEnter,
                    @AnimRes int animationOpenExit,
                    @AnimRes int animationCloseEnter,
                    @AnimRes int animationCloseExit)
backPressToClose(boolean backPressToClose);
stringResCopiedToClipboard(@StringRes int stringResCopiedToClipboard);
```

**WebView Options**
```java
webViewJavaScriptEnabled(boolean webViewJavaScriptEnabled);
webViewAppCacheEnabled(boolean webViewAppCacheEnabled);
webViewAllowFileAccess(boolean webViewAllowFileAccess);
webViewUseWideViewPort(boolean webViewUseWideViewPort);
webViewLoadWithOverviewMode(boolean webViewLoadWithOverviewMode);
webViewDomStorageEnabled(boolean webViewDomStorageEnabled);
webViewDisplayZoomControls(boolean webViewDisplayZoomControls);
webViewBuiltInZoomControls(boolean webViewBuiltInZoomControls);
webViewDesktopMode(boolean webViewDesktopMode);
```

**Builder Pattern**
```java
new FinestWebView.Builder(activity)
    .titleDefault("Default Title")
    .toolbarScrollFlags(AppBarLayout.LayoutParams.SCROLL_FLAG_SCROLL | AppBarLayout.LayoutParams.SCROLL_FLAG_ENTER_ALWAYS)
    .gradientDivider(false)
    .dividerHeight(100)
    .toolbarColorRes(R.color.accent)
    .dividerColorRes(R.color.black_30)
    .iconDefaultColorRes(R.color.accent)
    .iconDisabledColorRes(R.color.gray)
    .iconPressedColorRes(R.color.black)
    .progressBarHeight(DipPixelHelper.getPixel(context, 3))
    .progressBarColorRes(R.color.accent)
    .backPressToClose(false)
    .setCustomAnimations(R.anim.activity_open_enter, R.anim.activity_open_exit, R.anim.activity_close_enter, R.anim.activity_close_exit)
    .show(url);
```


## More customizations

#### Status Bar Color & Toolbar Color

Status bar color will be set as `colorPrimaryDark` of FinestWebViewActivity's theme.  
Toolbar color will be set as `colorPrimary` of FinestWebViewActivity's theme.  
But, you can override theses settings using builder option `statusBarColor`, `statusBarColorRes`, `toolbarColor`, `toolbarColorRes`.


#### Disable Toolbar Collapsing

```java
new FinestWebView.Builder(activity)
    .toolbarScrollFlags(0) // By sending as 0, toolbar collapsing will be disabled
    .show(url);
```


#### Collapsing Toolbar vs WebView BuiltInZoomControls
If you enable BuiltInZoomControls `webViewBuiltInZoomControls(true)`, it will automatically disable toolbar collapsing.


#### Full Screen Mode

```xml
<style name="AppTheme.NoActionBar.FullScreen" parent="AppTheme.NoActionBar">
    <item name="android:windowContentOverlay">@null</item>
    <item name="android:windowFullscreen">true</item>
</style>
<activity
    android:name="com.thefinestartist.finestwebview.FinestWebViewActivity"
    android:theme="@style/AppTheme.NoActionBar.FullScreen" />
```


#### Customizing Animations

You can use some pre-defined animations from this library or your own animations.

```java
new FinestWebView.Builder(activity)
    .setCustomAnimations(R.anim.activity_open_enter, R.anim.activity_open_exit, R.anim.activity_close_enter, R.anim.activity_close_exit)
    .show(url);
```

Pre-defined animation sets

```java
.setCustomAnimations(R.anim.activity_open_enter, R.anim.activity_open_exit, R.anim.activity_close_enter, R.anim.activity_close_exit)
.setCustomAnimations(R.anim.fragment_open_enter, R.anim.fragment_open_exit, R.anim.fragment_close_enter, R.anim.fragment_close_exit)
.setCustomAnimations(R.anim.slide_up, R.anim.hold, R.anim.hold, R.anim.slide_down)
.setCustomAnimations(R.anim.slide_left_in, R.anim.hold, R.anim.hold, R.anim.slide_right_out)
.setCustomAnimations(R.anim.fade_in_fast, R.anim.fade_out_medium, R.anim.fade_in_medium, R.anim.fade_out_fast)
```


#### Orientation Support

Use configChange, screenOrientation to customize your orientation options

```xml
<activity
    android:name="com.thefinestartist.finestwebview.FinestWebViewActivity"
    android:configChanges="keyboardHidden|orientation|screenSize"
    android:screenOrientation="sensor"
    android:theme="@style/FinestWebViewTheme" />
```

#### Gradient Divider

You can make your divider gradient. If you do, webview will be under the gradient. If you disable gradient divider, webview will be below the divider.

```java
new FinestWebView.Builder(activity)
    .gradientDivider(false)
    .show(url);
```


#### Custom Typeface

You can use your own typeface for title, url, and menus. You have to add your font file in `assets/fonts` folder.

```java
new FinestWebView.Builder(activity)
    .titleFont("Roboto-Medium.ttf")
    .urlFont("Roboto-Regular.ttf")
    .menuTextFont("Roboto-Medium.ttf")
    .show(url);
```


## Designer

#### [Min Kim](https://github.com/openyourboxes)

* User Interface Design
* Graphic Design


## License

```
The MIT License (MIT)

Copyright (c) 2013 TheFinestArtist

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```
