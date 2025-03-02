---
layout: default-layout
title: Dynamsoft Barcode Reader for Java SDK - Release Notes v7.6.0 and below
description: This is the release notes page of Dynamsoft Barcode Reader for Java SDK v7.6.0 and below.
keywords: release notes, java
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# Release Notes for Java SDK - 7.6.0 and below

## 7.6.0 (09/01/2020)

### NEW

- Added Mac library into the JAR file to support macOS platform. The Java SDK now supports Windows, Linux and macOS.
- Added a new member rpmColourArgumentIndex in the struct IntermediateResult. The rpmColourArgumentIndex is the index of ForeAndBackgroundColour argument used for RegionPredetectionMode.

### IMPROVED

- Improved the decoding speed for when ScanDirectly mode is enabled for localization.
- Improved the decoding speed by utilizing SIMD (single instruction, multiple data).
- Improved the deblurring algorithm for linear barcodes.

### FIXED

- Fixed a bug where the coordinates of barcodes are calculated incorrectly under some situations.
- Fixed a crash issue which occurs under some situations.

## 7.5.0(07/22/2020)

### NEW

- Added support for QR Code Model 1 (an older version of the QR Code specification). It can be enabled by setting FormatSpecification.EnableQRCodeModel1 in the JSON template file.
- Added a new localization mode LM_CENTRE to localize barcodes from the centre, which can improve the localization speed if the barcode is in the centre of the image. It can be enabled by setting the struct PublicRuntimeSettings -> LocalizationModes -> LM_CENTRE.
- Added a new binarization mode BM_THRESHOLD to set the BinarizationThreshold value which is used to convert the grayscale image to binary image.
- Added startPatternRange, middlePatternRange and endPatternRange properties to the struct OneDCodeDetails for UPC_A, UPC_E, EAN_8 and EAN_13 codes.
- Added the following new arguments for RegionPredetectionMode.RPM_GENERAL_RGB_CONTRAST and RegionPredetectionMode.RPM_GENERAL_GRAY_CONTRAST:
 - RelativeBarcodeRegions: Sets the barcode regions relative to the pre-detected region.
 - ForeAndBackgroundColours: Specifies a set (or multiple sets) of the foreground and background colours used for region pre-detection algorithm.
 - AspectRatioRange: Sets the height range of the bounding rectangle of the pre-detected region.
 - HeightRange: Sets the width range of the bounding rectangle of the pre-detected region.
 - WidthRange: Sets the aspect ratio range of the bounding rectangle of the pre-detected region.

### IMPROVED

- Optimized the binarization process for 1D barcode zones.
- Improved the decoding accuracy for 1D barcodes.
- Improved the decoding speed by 5%-20%.
- Improved the decoding accuracy for Data Matrix code with broken finder pattern.

### FIXED

- Fixed a bug where the coordinates of barcodes are calculated incorrectly under some situations.

## 7.4.0 (04/16/2020)

### NEW

- Added new barcode format support for DotCode.
- Added relative ROI (Region of Interest) detection to optimize the localization results in the high colour contrasted scenarios.
- Added a new type of output IRT_PREDETECTED_QUADRILATERAL, to identify regions with user-define HSV colour space.
- Implemented a feature for recognizing distorted DataMatrix barcodes. It can be enabled by turning on the struct PublicRuntimeSettings -> furtherMode -> DeformationResistingModes.
- Added an optimized decoding method for linear barcodes in vector PDF files. The vector PDF file can be decoded without rasterizing, increase decoding efficiency.
- Added two Enumerations for FrameDecodingParameters: ClarityCalculationMethod and ClarityFilterMode, to improve input image quality.
- Added a new image pre-processing mode IPM_MORPHOLOGY for barcodes with wide data bar or data cell gaps.

### IMPROVED

- Enhanced QR Code deformation, resistance, to improve the success rate of decoding the QR code with square symbol at the center.
- Optimized the algorithm for decoding large and dense QR and DataMatrix codes.
- Optimized deblurring algorithm for linear barcodes.
- Combined Windows and Linux Java libraries into one JAR file to support both platforms. The JAR file is also available on Dynamsoft server for developers to add dependencies easily via Maven repositories.
- Improved a character display issue on some platforms where BarcodeText returns an extra "\uFEFF" if the barcode is encoded in UTF-8 with BOM (Byte Order Mark).
- Simplified the process to enable DPM, DotCode and Postal Codes. Now the library will automatically turn on the corresponding localization mode while following settings are applied:
 - DPMCRM_GENEARL
 - BF2_DOTCODE
 - BF2_POSTALCODE

### FIXED

- Fixed a bug where the BinarizationModes settings do not work in the DPM mode.
- Fixed a bug where the barcode location returns incorrect when the barcode is close to the border of the scanning region.
- Fixed a bug in the calculation of deblur confidence.
- Fixed a bug where the ColourConversionModes RGB weights setting does not work when CICM_GENERAL is enabled.
- Other small fixes and tweaks.

## 7.3.0 (01/02/2020)

### NEW

- Added a new barcode type Postal codes including USPS Intelligent Mail, Postnet, Planet, Australia Post barcode, RM4SCC.
- Added a new localization mode LM_STATISTICS_POSTAL_CODE in the struct PublicRuntimeSettings -> LocalizationModes to recognize Postal codes.
- Added the capability to obtain accompanying texts at the top or bottom of a linear barcode. It can be enabled by turning on the struct PublicRuntimeSettings -> FurtherModes -> AccompanyingTextRecognitionModes.
- Implemented the feature of recognizing distorted QR barcode. It can be enabled by turning on the struct PublicRuntimeSettings -> FurtherModes -> DeformationResistingModes.
- Implemented the feature of complementing missing parts of QR Code & DataMatrix barcodes. It can be enabled by turning on the struct PublicRuntimeSettings -> FurtherModes -> BarcodeComplementModes.
- Added a new setting AutoFilter to set whether to filter frames automatically in the struct FrameDecodingParameters.
- Added a new setting ScaleUpModes to set the scale-up mode for linear barcodes with small module size. It can be enabled by turning on the struct PublicRuntimeSettings -> ScaleUpModes.

### IMPROVED

- Improved the decoding accuracy for DataMatrix that has a narrow quiet zone.
- Improved the decoding accuracy for 1D barcode that has a small module size.

## 7.2.2 (11/13/2019)

### FIXED

- Fixed a bug where BarcodeBytes was null when DPM mode was enabled.

## 7.2.1 (11/12/2019)

### NEW

- Added support for GS1-128 barcode.
- Added a new argument "RecordsetSizeOfLatestImages" for "IntermediateResultSavingMode" to specify how many sets of intermediate results are kept in the library.

### IMPROVED

- Improved the decoding capability of PDF417 by identifying the start and stop patterns of PDF417.
- Improved the deblurring performance for wide 1D barcodes, which lowers the possibility of fake results.
- Improved video decoding by optimizing frame filtering.
- Optimized the automatic classification for Code 39 and Code 39 Extended.
- Optimized the implementation of region pre-detection mode "RPM_GENERAL_GRAY_CONTRAST".
- Enhanced the recognition of barcodes with small module sizes.
- Changed ExtendedBarcodeFormatIds to BarcodeFormat_2 to support more barcode formats in the future.
- Improved the setting template inside every sample. For consistency, now every sample uses one of templates of "Best Coverage", "Balance" and "Best Speed".

### FIXED

- Fixed a bug in the barcode zone type identification during general statistical localization.
- Fixed minor bugs in result outputs.
- Fixed a bug where OneDCodeDetails doesn't work.

## 7.2.0 (09/24/2019)

### NEW

- Added more barcode formats:
 - GS1 Databar (Omnidirectional, Truncated, Stacked, Stacked Omnidirectional, Limited, Expanded, Expanded Stacked)
 - PatchCode
 - Maxicode (mode 2-5)
 - Micro PDF417
 - Micro QR
 - GS1 COMPOSITE (combination of OneD and PDF417/Micro PDF 417)
 - Non-standard Barcode
- Added the capability of reading DPM code. It can be enabled by turning on the struct PublicRuntimeSettings->furtherMode-> DPMCodeReadingModes and adding LM_STATISTICS_MARKS to the PublicRuntimeSettings->localizationModes.
- Licensing is required to obtain the intermediate results, except the original image in the intermediate results.
- Added a parameter, clarity in the struct ExtendedResult, to show the clarity of the decoded-barcode zone.
- Added a method, getModeArgument(), to get the argument value of the mode parameters.

### IMPROVED

- Improved the decoding speed for PDF417.
- Improved the capability of decoding QR and Data Matrix with cylinder-like deformation.

### FIXED

- Fixed minor bugs

## 7.1.0 (08/15/2019)

### NEW

- Added automatic blurry frame filtering for the video frame decoding, reducing incorrect barcode recognition.
- Added three arguments for the CICM_GENERAL of ColourConversionModes to set the weights for the color conversion, providing more flexibility to deal with various kinds of backgrounds by using different weights of three colors: red, green and blue.

### IMPROVED

- The output of intermediate results can be saved either directly to a folder or to memory or both, by introducing a new parameter, intermediateResultSavingMode, to the struct PublicRuntimeSettings.

### FIXED

- Updated PDF component to v10.3.2.0806
- Fixed a bug that the deblur function might malfunction in some rare cases.
- Fixed a bug that the coordinates of barcodes may be calculated incorrectly under some situations.
- Fixed a bug that the parameter, RequireStartStopChars, might malfunction in some rare cases.
- Fixed a bug that the angle of barcodes might not be calculated correctly sometimes.

## 7.0.0 (07/11/2019)

### NEW

- Refactored most modules to provide a flexible barcode reading framework that allows for parameter customization suited for a variety of barcode scenarios.
- Enabled access to intermediate results (grayscale image, binarized image, text zone, etc) during the decoding process.
- Added new interfaces to support video decoding, and frame decoding to improve interactive sensitivity.
- Provided methods to terminate the decoding process at different phases such as during binarization, localization or barcode type identification.
- Added a new barcode localization method, Scan Directly, to reduce decoding time significantly for high-quality images.

### IMPROVED

- Enhanced error messages related to the license initiation failure.
- Improved detailed results for decoded barcodes, including more barcode format specification.
- Improved results output to enable outputting barcode results in the order of confidence level, barcode position or format.

### FIXED

- Fixed an issue where the barcode could be calculated incorrectly in some occasions.

## 6.5.3 (07/03/2019)

### FIXED

- Updated the license verification process for development license and desktop runtime license. The old license verification process may lead to license error on some computers.
- Small fixes and tweaks.

## 6.5.2 (05/28/2019)

### IMPROVED

- Optimized barcode reading workflow for QRCode/DataMatrix/Aztec code recognition. A QRCode/DataMatrix/Aztec barcode zone will be submitted to the deblurring process when its decoding results vary with different binarization arguments.
- Reduced the error rate of 1D barcode recognition. Giving more chances for confirmation of a 1D barcode decoding result whose confidence isn’t extreme high.
- Reduced the possibility of conflicts with neighbour barcodes. This improved the precision of the zone to be deleted when a barcode is recognized successfully.

### FIXED

- Enhanced the robustness of the image processing algorithm. This resolved segmentation faults when a 0-size image is passed to our SDK or there are a few small-size barcode zones which need to do spatial transformation.

## 6.5.1 (04/16/2019)

### IMPROVED

- Improved deblur algorithm for OneD, enhancing the recognition rate for blurry/out-of-focus barcodes.
- Improved the accuracy of border location and symbol segmentation for AZTEC.
- Optimized line scanning algorithm for OneD, decreasing the computation load for character recognition.
- DecodeBuffer now supports 48-bit and 64-bit image data.

### FIXED

- Small fixes and tweaks.

## 6.5.0 (02/26/2019)

### IMPROVED

- Improved average reading speed by 5-10%.
- Greatly improved the image-processing performance for blurry PDF417 codes.
- Improved decoding performance for blurry 1D, QRCode and DataMatrix codes.
- Decreased error recognition rate for Aztec codes.

### FIXED

- Small fixes and tweaks.

## 6.4.1 (11/22/2018)

### IMPROVED

- Improved the decoding performance for Aztec, increasing the recognition rate.
- Improved the decoding performance for OneD, decreasing the error recognition rate.
- Added further check points for Timeouts, enhancing the timeout control on large scale images for decoding.

### FIXED

- Small fixes and tweaks.

## 6.4.0 (10/15/2018)

### NEW

- Added a BatchDecode tool which helps developers evaluate the recognition performance and speed of the Dynamsoft Barcode Reader SDK.
- Added a new sample demonstrates how to use Dynamsoft Barcode Reader in multiple threads.

### IMPROVED

- Improved barcode reading speed by 10%, especially for small-sized images.
- Reorganized API documentation to help you find content more easily.
- Simplified Developer's Guide to guide you through creating a HelloWorld project more quickly.

### FIXED

- Small fixes and tweaks.

## 6.3.0 (08/16/2018)

### NEW

- Added the support for Aztec codes.
- New developer's guide (.pdf) to cover common use cases,and re-worked existing PDF content to improve its usability.
- New API documentation (.chm) to help you find content more easily.
- Added GetRuntimeSettings and UpdateRuntimeSettings to help you adjust runtime barcode reading settings.
- Added ResetRuntimeSettings to reset runtime barcode reading settings to default values.
- Added InitRuntimeSettingsWithString and InitRuntimeSettingsWithFile to initialize barcode reading settings at runtime.
- Added OutputSettingsToString and OutputSettingsToFile to review runtime barcode reading settings.
- Added AppendTplStringToRuntimeSettings and AppendTplFileToRuntimeSettings to append a new template string/file to the current runtime settings.

### IMPROVED

- Improved the logic for ExpectedBarcodesCount. Previously the barcodes it returned may be greater than the given value of ExpectedBarcodesCount. Now as long as the expected barcodes found, it will stop continue searching and decoding barcodes.

### FIXED

- Small fixes and tweaks.

## 6.2.0 (06/28/2018)

### IMPROVED

- Decreased misreading rate for 1D barcodes.
- Enhanced performance for reading multiple barcodes from an image.
- Greatly improved recognition rate for QR Code and DataMatrix on complicated backgrounds.
- Greatly improved recognition rate for barcodes on grid background.
- Optimized localization for PDF417 without enough quiet zone.

### NEW RESOURCES

- New console samples – Decode Single Barcode, Decode Multi-Barcodes, Read Barcode from Region, Trigger Event after Decoding - are now available in the installer.

### FIXED

- Small fixes and tweaks.

## 6.1.0 (05/14/2018)

### NEW

- Added GetTemplateSettings and SetTemplateSettings methods which allow you to review and adjust barcode reading settings at runtime.

### IMPROVED

- Improved localization algorithm for barcodes rotated in a degree or with poor perspective.
- Faster read speed for QR, Data Matrix and PDF417 barcodes.

## 6.0.0 (03/30/2018)

### NEW

- Easy and flexible to create a custom barcode reading template for your specific use case.

### IMPROVED

- Improved average reading speed by 50% in a four-core CPU environment.
- Improved the reading accuracy and speed for blurred QRCode and DataMatrix.
- Improved the speed for reading barcodes directly from a computer/phone screen.
- Improved reading speed for small barcodes in high-resolution images.

### FIXED

- Small fixes and tweaks.

## 5.2.0 (09/08/2017)

### IMPROVED

- Improved the localization and recognition algorithms for PDF417 barcodes.
- Optimized the de-blur algorithm for 1D barcodes to improve the recognition accuracy.
- Optimized the timeout support. Now it is possible to stop barcode recognition by timeout.
- Increased QR Code and DataMatrix barcode recognition speed for B&W images.

### FIXED

- Small fixes and tweaks.

## 5.1.0 (05/25/2017)

### FIXED

- Fixed a bug that caused incorrect result points if de-blur algorithm is used when reading 1D barcodes.
- Other small fixes and tweaks.

## 5.0.0 (03/07/2017)

### NEW

- New de-blur algorithm for 1D barcodes to improve the accuracy when scanning linear barcodes from out-of-focus, blurred images.
- New multi-thread processing to improve the scanning accuracy and speed of 1D and PDF417 barcodes.
- Added new APIs that enable you to specify page numbers, barcode regions, barcode width, barcode height, barcode module size and barcode angles for barcode detection. These greatly improve the decoding workflow and barcode reading efficiency.
- Added ImageCaptureDevice API to set the capture device (scanner, camera or fax) being used to scan barcode images. When set, it will use a better and more appropriate image processing technique to the images captured from that device.
- Added TimeoutPerPage API to set the maximum amount of time for reading barcodes on one page.
- Added BarcodeColorMode API to set the ink color for barcodes searching.
- Added BarcodeTextEncoding API to set barcode text encoding mode so that you can display special characters properly.
- Added ReturnUnrecognizedBarcode API to set whether to return unrecognized barcodes.
- Added LoadSetting API so that you can now load the settings to be used in recognizing barcodes from a JSON string.
- Added Angle API to set the angle ranges of barcodes for scanning.
- Added Angle property to return the rotation angle of a detected barcode.

### FIXED

- Fixed an issue where the DLL crashes when reading DataMatrix in multiple threads.
- Other small fixes and tweaks.

## 4.3.0 (10/13/2016)

### NEW

- New localization algorithm was implemented for 1D barcode scanning to improve barcode reading speed.
- New multi-thread processing was implemented for 2D barcode reading to improve decoding accuracy.

### IMPROVED

- Improved recognition for perspective QR Codes.
- Optimized decoding performance for large size, special angle and multiple 1D barcodes.
- Improved sample applications to support Visual Studio 2015.
- Other small fixes and tweaks.

### NEW RESOURCES

- New samples are now available in the Code Gallery:
 - RESTful Web Service - implements server-side RESTful web service in C# for barcode reading.
 - HelloWorld - reads barcodes from a sample image in a Java web application.
 - Read barcode from mobile webcam - reads barcodes from photos captured from mobile webcam in Java on the mobile phones or tablets.

## 4.2.0 (04/08/2016)

### IMPROVED

- Changed 1D barcode decoding module to improve recognition accuracy.
- Improved ResultPoints Property to adjust the sequence of barcode corner points. Now the top-left corner of the barcode is the starting point (x1, y1). The results are returned in the clockwise direction.
- Improved ResultPoints Property to adjust the sequence of barcode corner points.

## 4.1.0 (01/21/2016)

### NEW

- Added Error Code -10022: "PDF Rasterizer DLL Missing".

### IMPROVED

- Improved positioning algorithm to better identify and localize DataMatrix barcodes.

## 4.0.0 (11/03/2015)

### NEW

- Added support for reading PDF417 and DataMatrix.
- Added reading barcode from all types of PDF file.

## 3.0.0 (08/13/2015)

### NEW

- Added 2D Barcode Reader to support reading QR Code.

### IMPROVED

- Improved 1D Barcode Reader to support reading Industrial 2 of 5.

## 2.1.0 (06/23/2015)

### NEW

- Reading image format of GIF is supported.

### IMPROVED

- Improved CODE128 decoding
- Improved recognition of CODE39, CODE93, etc.

## 2.0.0 (05/12/2015)

### NEW

- Dynamsoft Barcode Reader is now made available as a standalone product, in addition to working as an add-on for Dynamic Web TWAIN and Dynamic .NET TWAIN SDKs.
- Windows Edition: provides C, C++, ActiveX / COM and .NET APIs.
- Supported barcode types now include:
 Code39, Code128, Code93, Codabar, ITF, EAN13, EAN8, UPCA and UPCE
- Supported image formats include BMP, JPG, PNG, (single or multi-page) TIFF, Windows DIB and .NET Bitmap.
- Various code samples (in C/C++/C#/Java/VB/VB.NET) available. 

## 1.0.0 (01/20/2015)

### NEW

- Dynamsoft’s barcode recognition engine has been in existence since April, 2012. It works as an add-on to our Dynamic Web TWAIN and Dynamic .NET TWAIN SDKs. In this new release, we are changing the product name to Dynamic Barcode Reader and the version to 1.0.
- Updates in this version include 1D barcode improvements in accuracy and performance for Code 39 and Code128 recognition. Also image preprocessing is improved. For Code 128, the recognition ratio and speed have jumped up by as much as 30 percent.