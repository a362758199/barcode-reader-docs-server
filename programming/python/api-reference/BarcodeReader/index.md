---
layout: default-layout
title: Dynamsoft Barcode Reader Python API Reference - BarcodeReader Methods
description: This page shows BarcodeReader Methods of Dynamsoft Barcode Reader for Python SDK.
keywords: methods, BarcodeReader, api reference, python
needAutoGenerateSidebar: true
---

# class BarcodeReader


## Constructor and Destructor
   
  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](constructor-and-destructor.md#barcodereader) | Constructor of `BarcodeReader` object.|


## License
  
  | Method               | Description |
  |----------------------|-------------|
  | [`init_license`](license.md#init_license) | Reads product key and activates the SDK.  |
  | [`get_idle_instances_count`](license.md#get_idle_instances_count) | Gets available instances count when charging by concurrent instances count. |
  | [`set_device_friendly_name`](license.md#set_device_friendly_name) | Sets a human-readable name that identifies the device. |
  | [`init_license_from_server`](license.md#init_license_from_server) | `Deprecated` |
  | [`init_license_from_license_content`](license.md#init_license_from_license_content) | `Deprecated` |
  | [`output_license_to_string`](license.md#output_license_to_string) | `Deprecated` |
  | [`init_dls_connection_parameters`](license.md#init_dls_connection_parameters) | `Deprecated` |
  | [`init_license_from_dls`](license.md#init_license_from_dls) | `Deprecated` |
  | [`init_lts_connection_parameters`](license.md#init_lts_connection_parameters) | `Deprecated` |
  | [`init_license_from_lts`](license.md#init_license_from_lts) | `Deprecated` |



## Decode
   
  | Method               | Description |
  |----------------------|-------------|
  | [`decode_file`](decode.md#decode_file) | Decodes barcodes from a specified image file. |
  | [`decode_buffer`](decode.md#decode_buffer) | Decodes barcodes from the memory buffer containing image pixels in defined format.  |
  | [`decode_file_stream`](decode.md#decode_file_stream) | Decodes barcodes from an image file in memory. |
  | [`decode_buffer_manually`](decode.md#decode_buffer_manually) | Decodes barcodes from the memory buffer containing image pixels in defined format. |
  | [`decode_base64_string`](decode.md#decode_base64_string) | Decodes barcodes from the base64 encoded string. |
  | [`init_intermediate_result`](decode.md#initintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`decode_intermediate_results`](decode.md#decodeintermediateresults) | Decodes barcode from intermediate results. |

## Basic Settings Functions
   
  | Method               | Description |
  |----------------------|-------------|
  | [`set_mode_argument`](parameter-and-runtime-settings-basic.md#set_mode_argument) | Sets the optional argument for a specified mode in Modes parameters. |
  | [`get_mode_argument`](parameter-and-runtime-settings-basic.md#get_mode_argument) | Gets the optional argument for a specified mode in Modes parameters.  |
  | [`get_runtime_settings`](parameter-and-runtime-settings-basic.md#get_runtime_settings) | Gets current runtime settings. |
  | [`update_runtime_settings`](parameter-and-runtime-settings-basic.md#update_runtime_settings) | Update runtime settings with a given struct. |
  | [`reset_runtime_settings`](parameter-and-runtime-settings-basic.md#reset_runtime_settings) | Resets all parameters to default values. |

## Advanced Settings Functions
  
  | Method               | Description |
  |----------------------|-------------|
  | [`init_runtime_settings_with_file`](parameter-and-runtime-settings-advanced.md#init_runtime_settings_with_file)  | Initializes runtime settings with the settings in a given JSON file. |
  | [`init_runtime_settings_with_string`](parameter-and-runtime-settings-advanced.md#init_runtime_settings_with_string) | Initializes runtime settings with the settings in a given JSON string. |
  | [`append_template_file_to_runtime_settings`](parameter-and-runtime-settings-advanced.md#append_template_file_to_runtime_settings) | Appends a new template file to the current runtime settings. |
  | [`append_template_string_to_runtime_settings`](parameter-and-runtime-settings-advanced.md#append_template_string_to_runtime_settings) | Appends a new template string to the current runtime settings. |
  | [`get_all_template_names`](parameter-and-runtime-settings-advanced.md#get_all_template_names) | Gets the parameter templates name array. |
  | [`output_settings_to_json_file`](parameter-and-runtime-settings-advanced.md#output_settings_to_json_file) | Outputs runtime settings to a settings file (JSON file). |
  | [`output_settings_to_json_string`](parameter-and-runtime-settings-advanced.md#output_settings_to_json_string) | Outputs runtime settings to a string. |

## Video

### Decode
    
   | Method               | Description |
   |----------------------|-------------|
   | [`start_video_mode`](video.md#start_video_mode) | Starts a new thread to decode barcodes from the inner frame queue. |
   | [`append_video_frame`](video.md#append_video_frame) | Appends a frame image buffer to the inner frame queue. |
   | [`stop_video_mode`](video.md#stop_video_mode) | Stops the frame decoding thread created by start_video_mode(). |

### Parameter
   
   | Method               | Description |
   |----------------------|-------------|
   | [`init_frame_decoding_parameters`](video.md#init_frame_decoding_parameters) | Initializes frame decoding parameters. |


### Status retrieval
   
   | Method               | Description |
   |----------------------|-------------|
   | [`get_length_of_frame_queue`](video.md#get_length_of_frame_queue) | Gets length of current inner frame queue. |

## `BarcodeReader` Attributes
  
  | Attribute            | Description |
  |----------------------|-------------|
  | `version`  | dbr-python version |
  | `dbr_version`  | Dynamsoft Barcode Reader version |


## Result
  
  | Method               | Description |
  |----------------------|-------------|
  | [`get_intermediate_results`](result.md#get_intermediate_results) | Get intermediate results.  |
