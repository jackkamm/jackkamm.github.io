# Notes

## Installing and running jekyll in a local environment

From the Arch [wiki](https://wiki.archlinux.org/index.php/Ruby#Bundler):

```{sh}
# install ruby and bundler
sudo pacman -S ruby ruby-bundler
# configure bundler to not install systemwide
bundle config path ~/.gem
# start a new bundle and create Gemfile
bundle init
# add jekyll to Gemfile
echo 'gem "jekyll"' >> Gemfile
# install gems to .bundle
bundle install --path .bundle
# finally, run jekyll
bundle exec jekyll serve
```

2021-07-19: If getting error:

```
cannot load such file -- webrick (LoadError)
```

do 

```
bundle add webrick
```

See also:

https://stackoverflow.com/questions/65989040/bundle-exec-jekyll-serve-cannot-load-such-file

## Notes 2021-11-22

When I tried to run `bundle exec jekyll serve` today, I got the
following error:

```
/home/jack/Documents/jackkamm.github.io/.bundle/ruby/3.0.0/gems/ffi-1.15.3/lib/ffi.rb:3:in `require': cannot load such file -- 3.0/ffi_c (LoadError)`
```

This was probably due to updated libraries on my Arch system?

I fixed it doing `mv .bundle .bundle.bak` and rerunning the `bundle
config` and `bundle install` commands above.
