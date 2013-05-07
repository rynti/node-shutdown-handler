Node.js Shutdown Handler
========================

Creates the ability to execute code upon closing a Node.js application.

## Installation

```sh
$ npm install shutdown-handler
```


## Usage

In order to simply execute code prior to closing the application, add an event listener for the `exit` event:

```node
require('shutdown-handler').on('exit', function() {
  console.log("Shutdown...");
});
```

By default however, the application gets automatically closed after the events have been triggered. In order to avoid this default behaviour, simply execute the `preventDefault` function on the passed event object:

```node
require('shutdown-handler').on('exit', function(e) {
  e.preventDefault();
  console.log("This application shall not be closed!");
});
```


## Windows CTRL+C behaviour

The original usage for this module was to immediately close the application when I were to press CTRL+C in my console. Usually the console then asks if I'm sure whether I want to stop the current batch and that kind of annoyed me. So, in case you're sharing my opinion about this, you may use this module in order to make CTRL+C work properly.


## License

Copyright (c) 2013 Robert Böhm

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
