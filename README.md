# gitops
Scripts to assist with Github operations.

## gitclone

Clones all the repos from a specified org.

```
sudo curl -o /usr/local/bin/gitopsclone \
  https://raw.githubusercontent.com/anonyverse/gitops/master/bin/clone
sudo chmod 0755 /usr/local/bin/gitopsclone
```

**Usage**

You can clone all the repos in a specified github org by supplying
your personal access token and the Github org name either via
flags or as environmental variables. If you do not have your
GITHUB\_TOKEN as an environmental variable please store it in a
.github\_token file. For example, the following will clone all the
repos in this org:

```
gitopsclone -t $(cat .github_token) -o anonyverse
```

If you would like to test that your personal access token is
working for an org with private repos you have access to, you can
use `-r` to specify a single repo to attempt to clone. For example
in this repo you might try:

```
gitopsclone -t $(cat .github_token) -o anonyverse -r gitops
```

The above will _only_ clone this repo. (meta.)

For full usage, please run:

```
gitopsclone -h
```

**Caution**

Depening on the size and number of repositories in the
organziation that you specify, it may take a _long time_ to clone
all the repositories. If you are cloning large repositories please
be patient!
