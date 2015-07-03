# node-file-download
Download files with optional progress callback and unzip

## Install

```
$ npm install --save node-file-download
```


## Usage

If you're fetching an archive you can set `extract: true` in options and
it'll extract it for you.

```js
var download = require('node-file-download');

download('http://example.com/foo.zip',function(err,data){

})

download('http://example.com/foo.zip',function(err,data){
    console.log(err,data);
},function(data){
  console.log(data.progress);
})

#### options

##### options.url

Type: `string`  
URL for the file download

##### options.rename

Type: `string`  
Optional string to rename the file (extension should not be included)

##### options.directory

Type: `string`  
Default: `downloads`
Directory to download the file to. This can be relative, absolute or use environment variables

##### options.unzip

Type: `boolean`  
Default: `false`
If the file is a zip file, you can extract it by setting to true

##### options.unzipDirecory

Type: `string`  
Default: options.directory
The is where a zip file will be extracted to. This can be relative, absolute or use environment variables

##### options.unzipCleanup

Type: `boolean`  
Default: `false`
Setting to true will remove the original zip file after extraction


##### response

The [response object](http://nodejs.org/api/http.html#http_http_incomingmessage).

##### url

The requested URL.

### archive
An array of files (path and name) that were extracted from the zip file

### fileSizeMb
The size in MB of the downloaded file.

### filename
The filename of the downloaded file

### path
The absolute path to the downloaded file

### path
The absolute path to the downloaded file

### data
The data that was passed to the file.
