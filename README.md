# github-release

Upload releases to github.


## Example

Set the `GITHUB_TOKEN` environment variable in your `.profile` OR pass the token as an argument.

```js
'use strict';
const fs = require('fs');
const packageJ = require('./package.json');
var vfs = require('vinyl-fs');
const tarball = vfs.src('./dist.tar.gz');
const release = require('github-release');
const args = process.argv.slice(2);
const token = args[0] ? args[0] : undefined;
//Magic
tarball.pipe(release(packageJ, token));
```

## License

MIT
