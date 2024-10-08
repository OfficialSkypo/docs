---
id: valheim-backup-schedule
title: "Valheim: Enable automated backups for servers"
description: Information on how to enable and set up automated backups for your Valheim server from ZAP-Hosting - ZAP-Hosting.com documentation
sidebar_label: Automated Backups
services:
  - gameserver
---

import InlineVoucher from '@site/src/components/InlineVoucher';

<InlineVoucher />

Sadly Valheim is not offering a direct way to do automated Backups, so we need to use a little workaround. 

Navigate in your dashboard to "Restart Planner".

![image](https://screensaver01.zap-hosting.com/index.php/s/FspW5eG7XJNqE4k/preview)

Now click on the "+" it opens a new window, in which we can define the desired Restart times.

![image](https://screensaver01.zap-hosting.com/index.php/s/me5tSbwc8YWT7me/preview)

First we choose if desired "Daily", which means that on every day a backup will be created on the time we choose.
In the next step we define our desired restart time.

:::info
Start offline server - Means that your server will be started if its offline, when the reinstallation time is met.
:::

Now we click on "Save".

:::info
You could setup a planned restart all 6 hours, what means that all 6 hours a automated backup will be created.
:::

![image](https://screensaver01.zap-hosting.com/index.php/s/rFPWnSH7EkHxoN9/preview)
