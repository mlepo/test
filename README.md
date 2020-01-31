# AntennaPod 1947 - Diff example

```diff
From 2e467d07bfd2135e47a31752f8547a133793cdf5 Mon Sep 17 00:00:00 2001
From: Jens Klingenberg <Foso@users.noreply.github.com>
Date: Thu, 19 May 2016 00:02:30 +0200
Subject: [PATCH] Fix for restoring scroll position in detail view #1947

The scroll position on detail view is now being restored when you are switching back to it.

On orientation change it doesn't restore on the exact position at the moment.
But i think that could work with a scroll position relative to the webview height.
---
 .../de/danoeh/antennapod/fragment/ItemDescriptionFragment.java  | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)

diff --git a/app/src/main/java/de/danoeh/antennapod/fragment/ItemDescriptionFragment.java b/app/src/main/java/de/danoeh/antennapod/fragment/ItemDescriptionFragment.java
index 55d28cadb..94d61e075 100644
--- a/app/src/main/java/de/danoeh/antennapod/fragment/ItemDescriptionFragment.java
+++ b/app/src/main/java/de/danoeh/antennapod/fragment/ItemDescriptionFragment.java
@@ -348,7 +348,7 @@ private void savePreference() {
     }
 
     private boolean restoreFromPreference() {
-        if (!saveState) {
+        if (saveState) {
             Log.d(TAG, "Restoring from preferences");
             Activity activity = getActivity();
             if (activity != null) {
```
