This script to updates Git and SVN repos (i.e. `git pull` & `svn up`) checked out in the same directory. This is primarily intended for WordPress Core development, specifically for these two repos:

Git: `https://github.com/WordPress/wordpress-develop.git`  
SVN: `https://develop.svn.wordpress.org/trunk/`

Pass a branch name like `6.8` as the sole argument to check out that branch:

```bash
git svn-up 6.8
```

Or a feature branch:

```bash
git svn-up trac-1234
```

Otherwise, `trunk` is checked out if omitted:

```bash
git svn-up
```

This script was originally [developed](https://github.com/GoogleChromeLabs/wordpressdev/blob/master/bin/svn-git-up) in the [GoogleChromeLabs/wordpressdev](https://github.com/GoogleChromeLabs/wordpressdev) repo but was split into a separate repo via [git-filter-repo](https://github.com/newren/git-filter-repo).

Check out Felix Arntz's writeup: [My WordPress Core Contribution Workflow](https://felix-arntz.me/blog/my-wordpress-core-contribution-workflow/).

# Installation

```bash
sudo wget -O /usr/local/bin/svn-git-up https://raw.githubusercontent.com/westonruter/svn-git-up/refs/heads/main/svn-git-up
sudo chmod +x /usr/local/bin/svn-git-up
git config --global alias.svn-up '!svn-git-up $1'
```

# Repo Setup

Make a working directory and enter it:

```bash
mkdir wordpress-develop && cd wordpress-develop
```

Clone the Git repo:

```bash
git clone https://github.com/WordPress/wordpress-develop.git .
```

Check out the SVN repo:

```bash
svn co https://develop.svn.wordpress.org/trunk/ /tmp/wp-svn
mv /tmp/wp-svn/.svn .
```

Add a remote for your and set it as the origin remote for pushing:

```bash
git remote add westonruter https://github.com/westonruter/wordpress-develop.git
git remote set-url --push origin https://github.com/westonruter/wordpress-develop.git
```
