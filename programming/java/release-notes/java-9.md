---
layout: default-layout
title: Dynamsoft Barcode Reader for Java Language - Release Notes v9.x
description: This is the release notes page of Dynamsoft Barcode Reader for Java Language v9.x.
keywords: release notes, java
needGenerateH3Content: false
---

# Release Notes for Java SDK - 9.x

## 9.4.0 (08/30/2022)

### Highlights

{%- include release-notes/product-highlight-9.4.0.md -%}

### Changelog

#### New

- Added an argument [`IsOneDStacked`]({{site.parameters_reference}}localization-modes.html#isonedstacked) to `LM_SCAN_DIRECTLY` to process stacked OneD barcodes.
- Added a parameter [`PatchCodeSearchingMargins`]({{site.parameters_reference}}patchcode-searching-margins.html) to specify the searching area of PatchCode.
- Added the supported data format of [`FormatSpecification.PartitionModes`]({{site.parameters_reference}}partition-modes.html) to enhance the readability of the parameters. Users can use a list of enumeration names to specify the `PartitionModes`.

#### Improved

- Improved the localization mode `LM_LINES` to better support skewed and perspective OneD barcodes.
- Enhanced tamper resistance of the license keys.

#### Deprecated

- Deprecated the attribute `barcodeFormatString_2` of [`TextResult`]({{site.java_class}}TextResult.html#barcodeformatstring_2), [`ExtendedResult`]({{site.java_class}}ExtendedResult.html#barcodeformatstring_2) and [`LocalizationResult`]({{site.java_class}}LocalizationResult.html#barcodeformatstring_2). All the barcode format strings will be returned by the attribute `barcodeFormatString`.

## 9.2.0 (06/07/2022)

<div class="fold-panel-prefix"></div>

### Version Highlights <i class="fa fa-caret-down"></i>

<div class="fold-panel-start"></div>

{%- include release-notes/product-highlight-9.2.0.md -%}

<div class="fold-panel-end"></div>

### Edition Highlights

- Added macOS ARM64 support to the Java edition of the SDK.

### Changelog

#### New

- Added a new method [`setDeviceFriendlyName`]({{site.java_methods}}license.html#setdevicefriendlyname) to set a human-readable name that identifies the device.

## 9.0.0 (03/15/2022)

<div class="fold-panel-prefix"></div>

### Version Highlights <i class="fa fa-caret-down"></i>

<div class="fold-panel-start"></div>

{%- include release-notes/product-highlight-9.0.0.md -%}

<div class="fold-panel-end"></div>

### Edition Highlights

- Added ARM64 Linux support to the Java edition of the SDK. In previous versions, Java Edition supported Windows x32/x64, macOS x64, and Linux x64.

### Changelog

#### New

- Added `BF_CODE_11` under Enumeration [`EnumBarcodeFormat`]({{ site.java_enumerations }}format-enums.html#barcodeformat) to specify newly supported barcode format, Code 11. 
- Added `BF2_PHARMACODE_ONE_TRACK`, `BF2_PHARMACODE_TWO_TRACK` and `BF2_PHARMACODE` under Enumeration [`EnumBarcodeFormat_2`]({{ site.java_enumerations }}format-enums.html#barcodeformat_2) to specify newly supported barcode format, Pharmacode. 
- Added a new error code [`DBRERR_PHARMACODE_LICENSE_INVALID`]({{ site.java_enumerations }}error-code.html#error-code--10062) which will be returned when the license of Pharmacode is invalid.
- Added `DRM_BROAD_WARP`, `DRM_LOCAL_REFERENCE` and `DRM_DEWRINKLE` under Enumeration [`EnumDeformationResistingMode`]({{ site.java_enumerations }}parameter-mode-enums.html#deformationresistingmode) to apply new deformation resisting modes.
- Added a parameter [`FormatSpecification.PartitionModes`]({{ site.parameters_reference }}partition-modes.html)
- Added a parameter [`FormatSpecification.VerifyCheckDigit`]({{ site.parameters_reference }}verify-check-digit.html)
- Added an Argument [`ConfidenceThreshold`]({{ site.parameters_reference }}localization-modes.html#confidencethreshold) to the `LocalizationModes` mode arguments.

#### Changed

- Changed method [`InitLicense`]({{ site.java_methods }}license.html#initlicense) to a static method.
- Changed value of BF_ONED under Enumeration [`EnumBarcodeFormat`]({{ site.java_enumerations }}format-enums.html#barcodeformat) to 0x003007FF to have BF_CODE_11 combined.
- Changed value of BF_ALL under Enumeration [`EnumBarcodeFormat`]({{ site.java_enumerations }}format-enums.html#barcodeformat) to 0xFE3FFFFF to have BF_CODE_11 combined.
- Changed the behaviour of [`DeformationResistingMode`]({{ site.java_enumerations }}parameter-mode-enums.html#deformationresistingmode) DRM_GENERAL which now only applies basic process to resist deformation.
- Changed the return value of the method [getIdleInstancesCount]({{ site.java_methods }}license.html#getidleinstancescount) from 0 to -1 when the available count needs to be updated from server by calling initLicense.


#### Fixed
- Fixed a bug that might cause a crash when using multiple threads for barcode decoding.
- Fixed a bug that throws exceptions when using method [getIdleInstancesCount]({{ site.java_methods }}license.html#getidleinstancescount).
- Fixed a bug that Function Code 1 (FNC1) character would not return if it was in the first position of GS1-128 codes.
- Other small fixes and tweaks.


#### Deprecated

The following items are now deprecated. They still work in this version but could be removed in the near future.
- Method [`initLicenseFromServer`]({{ site.java_methods }}license.html#initlicensefromserver)
- Method [`initLicenseFromLicenseContent`]({{ site.java_methods }}license.html#initlicensefromlicensecontent)
- Method [`outputLicenseToString`]({{ site.java_methods }}license.html#outputlicensetostring)
- Method [`initDLSConnectionParameters`]({{ site.java_methods }}license.html#initdlsconnectionparameters)
- Method [`initLicenseFromDLS`]({{ site.java_methods }}license.html#initlicensefromdls)
- Enumeration [`EnumDMChargeWay`]({{ site.java_enumerations }}other-enums.html#dm_chargeway)
- Enumeration [`EnumDMDeploymentType`]({{ site.java_enumerations }}other-enums.html#dm_deploymenttype)
- Enumeration [`EnumDMLicenseModule`]({{ site.java_enumerations }}other-enums.html#dm_licensemodule)
- Enumeration [`EnumDMUUIDGenerationMethod`]({{ site.java_enumerations }}other-enums.html#dm_uuidgenerationmethod)
- Enumeration [`EnumProduct`]({{ site.java_enumerations }}other-enums.html#product)


