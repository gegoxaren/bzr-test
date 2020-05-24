# This is just a test of pushing from a bazaar repo to github.

I'm not friends with Git, so this is is a test to see if I can do it with
Bazaar instead.

First you need to install bzr-git, this is done in Ubuntu via
`sudo apt install bzr-git'`

Then you have to push it, in this case this is what I did:

```
bzr push --lossy https://github.com/gegoxaren/bzr-test.git/,branch=master
```

The branch name is put in the end of the URL, in this case
`,branch=master`.
