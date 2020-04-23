# TTS Community Homepage

This is the homepage for the TTS (Tabletop Simulator) Community Github group, live at [tts-community.github.io](https://tts-community.github.io).

Contributions welcome!

## Contributing

If you've got some Tabletop Simulator knowledge you'd like; guides, libraries, links, assets, this is the place to share them.

### Via Github's Web Interface

If you're not familiar with Git, then small changes can be made directly in Github by navigating to the relevant page and pressing the "Edit this file" button

![Contributing via Github](https://tts-community.github.io/assets/images/edit-this-file.png)

### Via Git

If you're familiar with Git and/or you'd like to make larger contributions, then you'll want to fork this repository, clone it locally and submit a pull request.

#### Previewing Changes

You can preview your changes by [setting up Github Pages](https://help.github.com/en/github/working-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#choosing-a-publishing-source) for your fork, however a better solution is to get the page up and running locally on your computer.

To do this you'll need to have Ruby installed. From a command line with Ruby navigate to this directory and run Bundler to download the relevant dependencies: 

```bash
bundle
```

Start a local web server hosting the site: 

```bash
bundle exec jekyll serve
```

If you then navigate to [http://localhost:4000](http://localhost:4000) in your browser you will be able to view your changes locally.
