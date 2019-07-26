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
