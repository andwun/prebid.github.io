---
layout: userid
title: Trustpid
description: Trustpid User ID sub-module
pbjs_version_notes: not in 8.x
useridmodule: trustpidSystem
bidRequestUserId:
eidsource: 
example:
---

{: .alert.alert-info :}
This ID module has been renamed [utiq](/dev-docs/modules/userid-submodules/utiq.html) as of Prebid.js 8.0.

Trustpid generates unique tokens, enabling improved efficiency in programmatic advertising while safeguarding transparency and control for end customers via `trustpid.com`. A website visitor’s Trustpid is generated based on network identifiers provided by network operators and requires explicit user consent.

Trustpid is also the brand name of the service, which is provided by Vodafone Sales and Services Limited (“VSSL”).

## Trustpid configuration

{: .table .table-bordered .table-striped }

| Param under userSync.userIds[] | Scope | Type | Description | Example |
| --- | --- | --- | --- | --- |
| name | Required | String | The name of the module | `"trustpid"` |
| params | Required | Object | Object with configuration parameters for trustpid User Id submodule | - |
| params.maxDelayTime | Required | Integer | Max amount of time (in seconds) before looking into storage for data | 2500 |
| bidders | Required | Array of Strings | An array of bidder codes to which this user ID may be sent. Currently required and supporting AdformOpenRTB | `['adf']` |
| storage | Required | Object | Local storage configuration object | - |
| storage.type | Required | String | Type of the storage that would be used to store user ID. Must be `"html5"` to utilise HTML5 local storage. | `"html5"` |
| storage.name | Required | String | The name of the key in local storage where the user ID will be stored. | `"trustpid"` |
| storage.expires | Required | Integer | How long (in days) the user ID information will be stored. For safety reasons, this information is required.| `1` |

Configuration example:

```javascript
pbjs.setConfig({
  userSync: {
    userIds: [
      {
        name: "trustpid",
        params: {
          maxDelayTime: 2500,
        },
        bidders: ["adf"],
        storage: {
          type: "html5",
          name: "trustpid",
          expires: 1,
        },
      }],
    syncDelay: 3000,
    auctionDelay: 3000
  }
});
```

## Truspid onboarding

If you wish to find out more about Trustpid, please contact <onboarding@trustpid.com>
