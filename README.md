# This is just a test of pushing from a bazaar repo to GitHub and GitLab.

I'm not friends with Git, so this is is a test to see if I can do it with
Bazaar instead.

First you need to install bzr-git, this is done in Ubuntu via
`sudo apt install bzr-git`

We then need to add GitHub to the `~/.bazaar/authentication.conf` file:

```
[github.com]
scheme=https
host=github.com
user=gegoxaren
```

For GitLab we do something similar:

```
[gitlab.com]
scheme=https
host=gitlab.com
user=gustav.hartvigsson
```

Note: I did not put my password in the file, and that is something you should not
do, it is actively discouraged by Bazaar, and it will warn you.

Note: GitHub is moving away from allowing password authentication over https,
so we will need to add an ssh key to make it work.


Then you have to push it, in this case this is what I did, over https, you do
as follows:

```
bzr push --lossy https://github.com/gegoxaren/bzr-test.git/,branch=master

```

Using SSH:
```
bzr push ush git@github.com:gegoxaren/bzr-test.git,branch=master
```

Note: That instead of a slash followed by a comma at the end, there is just a
comma, and there is no need for the `--lossy` flag (It will not actually work
at all.)


Or on GitLab:

```
bzr push --lossy https://github.com/gustav.hartvigsson/bzr-test.git/,branch=master
```


The branch name is put in the end of the URL, in this case
`,branch=master`.

To push to a new remote-branch, we use a different branch name.
I will use `my-awesome-fix` for in this example.

```
bzr push --lossy https://github.com/gegoxaren/bzr-test.git/,branch=my-awesome-fix
```

This will create a new branch on github, and it is usable on github as any other
git branch when merging.

To create a local branch from a git branch, we do the following:

```
bzr branch https://github.com/gegoxaren/bzr-test.git/,branch=master
```

This will branch the git repo to a local branch called `bzr-test.git`, that is
perhaps not what you want, bit that is easy to fix by just putting a name after
it:


```
bzr branch https://github.com/gegoxaren/bzr-test.git/,branch=master bzr-test
```

This will branch to a local branch called bzr-test.


Of course this works with other branches as well:

```
bzr branch https://github.com/gegoxaren/bzr-test.git/,branch=my-awesome-fix bzr-test-my-awesome-fix
```

