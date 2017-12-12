# NativeScript Downloader

[![npm](https://img.shields.io/npm/v/nativescript-downloader.svg)](https://www.npmjs.com/package/nativescript-downloader)
[![npm](https://img.shields.io/npm/dt/nativescript-downloader.svg?label=npm%20downloads)](https://www.npmjs.com/package/nativescript-downloader)
[![Build Status](https://travis-ci.org//triniwiz/nativescript-downlaoder.svg?branch=master)](https://travis-ci.org/triniwiz/nativescript-downloader)

## Installation

```bash
tns plugin add nativescript-downloader
```

## Usage

```ts
import { Downloader } from 'nativescript-downloader';
const downloader = new Downloader();
const imageDownloaderId = downloadManager.createDownload({
  url:
    'https://wallpaperscraft.com/image/hulk_wolverine_x_men_marvel_comics_art_99032_3840x2400.jpg'
});

downloader
  .start(imageDownloaderId, (progressData: ProgressEventData) => {
    console.log(`Progress : ${progressData.value}%`);
  })
  .then((completed: DownloadEventData) => {
    console.log(`Image : ${completed.path}`);
  })
  .catch(error => {
    console.log(error.message);
  });
```

## Api

| Method                                   | Default | Type                         | Description                                           |
| ---------------------------------------- | ------- | ---------------------------- | ----------------------------------------------------- |
| createDownload(options: DownloadOptions) |         | `string`                     | Creates a download task it returns the id of the task |
| getStatus(id: string)                    |         | `StatusCode`                 | Gets the status of a download task.                   |
| start(id: string, progress?: Function)   |         | `Promise<DownloadEventData>` | Starts a download task.                               |
| retry(id: string)                        |         | `void`                       | Retries a download task.                              |
| resume(id: string)                       |         | `void`                       | Resumes a download task.                              |
| cancel(id: string)                       |         | `void`                       | Cancels a download task.                              |
| pause(id: string)                        |         | `void`                       | Pauses a download task.                               |
| getPath(id: string)                      |         | `void`                       | Return the path of a download task.                   |

## Example Image

| IOS                                     | Android       |
| --------------------------------------- | ------------- |
| ![IOS](https://i.imgur.com/WQqhhXF.gif) | _Coming Soon_ |

# TODO

* [ ] Local Notifications
