
https://antonybaasan.github.io/

(submodule - https://github.com/AntonyBaasan/antonybaasan.github.io)

Setup after clone:

``` 
# remove the public folder
rm -rf public

# will bring latest public directory 
git submodule update
```

Add posts:
```
hugo new blog/name-of-the-post
```

Development:
```
# Starts local server (-D includes drafts)
hugo server -D
```

Publish:
```
# build
hugo
cd public
--- commit and push ---
```

# Submodules

