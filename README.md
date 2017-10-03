# top-100-domains-ads-txt

The files in this repo are the results of running a Adx.txt crawler on the top 100 programmatic domains.

The domain list is is available here [https://gist.github.com/bradlucas/f5060dfc602cfeedb140a23bb4d77403](https://gist.github.com/bradlucas/f5060dfc602cfeedb140a23bb4d77403).

The Adx.txt crawler is the latest version of [https://github.com/bradlucas/ads-txt-crawler](dhttps://github.com/bradlucas/ads-txt-crawler).

The results were created on 10-03-2017. You'll notice that of the 100 about 40% of the sites have Ads.txt files.



## The Files

### Results

- [results.csv](results.csv)

This file is the output from the crawler. It contains all the data retrieved from Ads.txt files it found

### Errors

- [error.log](error.log)

This file shows issues that were found. Not all sites support the Ads.txt file.

## Domains with Ads.txt

- [domains-with-ads-txt.txt](domains-with-ads-txt.txt)

To generate this file you can use the following:

```
$ cat results.csv | cut -d, -f1 | sort | uniq > domains-with-ads-txt.txt
```

### Domains without Ads.txt

The domains which had Ads.txt files

- [domains-without-ads-txt.txt](domains-without-ads-txt.txt)

The file is generated with:

```
$ cat error.log | sed "s/.*http:\/\///" | cut -d/ -f1 | uniq | sort > domains-without-ads-txt.txt
```

Domains which did not have files

## License

Copyright © 2017 Brad Lucas

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.
