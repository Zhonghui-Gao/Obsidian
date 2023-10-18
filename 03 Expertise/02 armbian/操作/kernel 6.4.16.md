---
Date: 2023/10/18
result: okay
new: kernel
type: fixed bug
project: armbian
rating: ⭐⭐⭐
status: 🌲done
---

# patch 1
**target**：linux-6.4.16/include/net/bluetooth\hci.h

`nvim patch/misc/wireless-driver-for-uwe5622-park-link-v6.1-post.patch`

```shell
diff --git a/../hci.h b/hci.h
index 3ff822e..551654d 100644
--- a/../hci.h
+++ b/hci.h
@@ -310,6 +310,12 @@ enum {
 	 */
 	HCI_QUIRK_BROKEN_SET_RPA_TIMEOUT,
 
+	/*
+	 * Device declares that support Park link status, but it really
+	 * does not support it and fails to initialize
+	 */
+	HCI_QUIRK_BROKEN_PARK_LINK_STATUS,
+
 	/* When this quirk is set, MSFT extension monitor tracking by
 	 * address filter is supported. Since tracking quantity of each
 	 * pattern is limited, this feature supports tracking multiple

```

# patch2
**target**：linux-6.4.16/drivers/usb/typec/bus.c

`nvim  patch/kernel/archive/rockchip64-6.4/board-pbp-add-dp-alt-mode.patch`

```shell
diff --git a/../bus.c b/bus.c
index e95ec7e..1794b5a 100644
--- a/../bus.c
+++ b/bus.c
@@ -187,8 +187,11 @@ int typec_altmode_attention(struct typec_altmode *adev, u32 vdo)
 {
 	struct altmode *partner = to_altmode(adev)->partner;
 	struct typec_altmode *pdev;
+    
+    	WARN_ONCE(!adev, "typec bus attention: adev is NULL!");
+	WARN_ONCE(!partner, "typec bus attention: partner is NULL!");
 
-	if (!partner)
+	if (!adev || !partner)
 		return -ENODEV;
 
 	pdev = &partner->adev;

```

# patch3
**target**：arch/arm64/boot/dts/rockchip/rk3399-rock-pi-4.dtsi
`nvim  patch/kernel/archive/rockchip64-6.4/board-rockpi4-FixMMCFreq.patch`
[[kernel 6.4.16]] 已经将dts修复 将这个patch删除

