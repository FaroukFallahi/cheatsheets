# sed
These are some scenarios for using sed.

Let's say we have a set of package names like this:
```bash
package1:amd64 (1.2-3.9), package-two:amd64 (1.2.33-5), packagethree:amd64 (3.5.6-1.1-4)
```
Then we can remove everything but the package name using this:
```bash
$ cat regex_text | sed -E "s/:amd64[^,]+,/ /g"
```
