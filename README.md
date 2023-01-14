# Overview

This should serve as a tutorial on how to create itemlists for
[Fansort](https://floofnoodlecode.github.io/fansort/#/title?EOL=), an item sorter for user-defined itemlists.

This repository is also an itemlist collection that demonstrates all the features that you can use
for your custom itemlists. In order to see these features you can go to
https://floofnoodlecode.github.io/fansort/#/index/m8Q0jWF9Wk5-flpefn5KTmpyfkoq45q0xLzi_KIS3ZTU3HymJbmJmXkA?EOL=
to view the results.

Contents:
1. [Quickstart](#quickstart) - Teaches you the minimal information you need to know to create itemlists
2. [Reference](#reference) - Explains all the features that an itemlist can make use of

# Quickstart

This section will guide you through the process of creating a minimal itemlist from scratch. See the [Reference](#reference) section for in-depth detail of all the features.

## Setting up

We must first create a repository and obtain a Fansort link for our repo.

**Step 1**: Create a repository for your itemlist collection. I recommend naming it `fansort-*`, where `*` should be replaced with a name fitting for your collection.

**Step 2**: Create an `index.json` file into the root of the repo and add the following text to it:
```json
{
	"lists": []
}
```

**Step 3**: Copy your GitHub repository's URL.

**Step 4**: Go to the [Fansort Create page](https://floofnoodlecode.github.io/fansort/#/create?type=repo&EOL=)
and paste the copied URL into the first input box (*Root URL*)

**Step 5**: The app has generated the URL for your repo in the bottom text field.
It should look something like `https://floofnoodlecode.github.io/fansort/#/index/m8Q0jWF9Wk5-flpefn5KTmpyfkoq45q0xLzi_KIS3ZTU3HymJbmJmXkA?EOL=`.

**Step 6**: Go to that URL. It currently shows an empty page, since we still haven't added any itemlists.

# Reference
