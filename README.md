This script to updates Git and SVN repos (i.e. `git pull` & `svn up`) checked out in the same directory. This is primarily intended for WordPress Core development, specifically for these two repos:

Git: `https://github.com/WordPress/wordpress-develop.git`  
SVN: `https://develop.svn.wordpress.org/trunk/`

Pass a branch name like `6.6` as the sole argument to check out that branch. Otherwise, `trunk` is checked out.

This script was originally [developed](https://github.com/GoogleChromeLabs/wordpressdev/blob/master/bin/svn-git-up) in the [GoogleChromeLabs/wordpressdev](https://github.com/GoogleChromeLabs/wordpressdev) repo but was split into a separate repo via [git-filter-repo](https://github.com/newren/git-filter-repo).

Check out Felix Arntz's writeup: [My WordPress Core Contribution Workflow](https://felix-arntz.me/blog/my-wordpress-core-contribution-workflow/).
