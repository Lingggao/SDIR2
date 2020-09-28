# Software Defect Investigation Report

*This report uses machine translation to reduce the author's workload; please understand that some sentences may not flow smoothly or may be difficult to understand.*

[**中文版本 (Chinese Version)**](https://github.com/Lingggao/SDIR2/blob/master/README_CN.md#%E8%BD%AF-%E4%BB%B6-%E7%BC%BA-%E9%99%B7-%E8%B0%83-%E6%9F%A5-%E6%8A%A5-%E5%91%8A)

## I. Introduction

> From: Ling Gao ( KaiXiu Gao | 高楷修)  
> Title: Microsoft Windows Insider

> To: Microsoft

> Date: September 29, 2020

## II. Description

As of September 26, 2020, users of Windows 10 products in the People's Republic of China (including Hong Kong, Macau, and Taiwan) are experiencing this issue: **some of the text in the taskbar search menu has changed from Simplified Chinese (or Traditional Chinese) to English**.

### Problem reproduction steps:

1. Click on the "magnifying glass" search menu icon in the taskbar.

![Search](https://github.com/Lingggao/SDIR2/blob/master/1.png?raw=true)

2. Under normal circumstances, all text in the search menu will be displayed in Chinese.

<img src="https://github.com/Lingggao/SDIR2/blob/master/2.png?raw=true" width = "50%" />

3. Due to this issue, some of the text in the search menu will be displayed in English.

<img src="https://github.com/Lingggao/SDIR2/blob/master/3.png?raw=true" width = "50%" />

### Update:

As of 9:00 am, Seattle time on September 28, 2020, the problem can still be successfully reproduced. **Nearly 100 users of Windows products have already indicated in the Microsoft Community that they are suffering from this issue**. For a detailed summary of the issue, please see the Microsoft Community discussion post [**here**](https://answers.microsoft.com/zh-hans/windows/forum/all/2020-%e5%b9%b4-9-%e6%9c%88-26-%e6%97%a5/59ebb312-fbdd-4d6a-9e2a-c9eac7763125).

## III. Testing

**To cover as many Windows versions as possible, six Windows 10 devices were used for this test.**

1. Testing on a device running Windows 10 version 1903_18362.1082 with a search menu version of Build 2020.09.27.15535856, **the problem was successfully reproduced**.
2. Tested on a device running Windows 10 version 1909_18363.1016 with a search menu version of Build 2019.07.18.6227079, **the problem could not be reproduced**.
3. Tested on a device running Windows 10 version 1909_18363.1082 with a search menu version of Build 2019.07.18.6227079, **the problem could not be reproduced**.
4. Testing on a device running Windows 10 version 1909_18363.1082 with a search menu version of Build 2020.09.27.15535856, **the problem was successfully reproduced**.
5. Testing on a device running Windows 10 version 2004_19041.508 with a search menu version of Build 2020.09.25.15490140, **the problem was successfully reproduced**.
6. Tested on a device running Windows 10 Insider Preview Build 20221 with a search menu version of Build 2020.09.23.15409635, **the problem could not be reproduced**.
7. In conjunction with clues from users of other Windows products, this issue can occur in Windows 10 1903 - 2004 editions, **independent of the specific Windows system version**. This issue can also occur in the Search Menu Build 2020.09.25 - 2020.09.27, **again not limited to a specific internal version of the Search Menu**.
8. Rebooting the device does not resolve the issue, and reinstalling the same version of Windows does not resolve the issue.

| Windows Version | Search Menu Version | Reproducibility Issue |
| :-------------: | :-----------------: | :-------------------: |
| 1903_18362.1082 | 2020.09.27.15535856 |        **YES**        |
| 1909_18363.1016 | 2019.07.18.6227079  |          NO           |
| 1909_18363.1082 | 2019.07.18.6227079  |          NO           |
| 1909_18363.1082 | 2020.09.27.15535856 |        **YES**        |
| 2004_19041.508  | 2020.09.25.15490140 |        **YES**        |
|   Build 20221   | 2020.09.23.15409635 |          NO           |

## IV. Conclusion

The test work confirms that **this problem strongly correlates with the search menu's internal version number and a weak correlation with the Windows system version number. However, the specific cause of the problem is still unclear. We hope that Microsoft will conduct further investigation and handling of this issue as soon as possible**.

Finally, a big thank you to all the Microsoft engineers for their hard work, **Microsoft engineer** [**Jen**](https://twitter.com/JenMsft) and **Windows Insider MVP** [**Sumit**](https://twitter.com/_sumitdhiman) for their help, and all the Windows Insiders and product users who worked with us on this test.