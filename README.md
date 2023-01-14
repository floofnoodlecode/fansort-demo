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

Now that we have a fansort link, the changes that we will make in the repo will show up in the app.
Remember that if you want to visualize the changes after every step, you will need to **commit and push** the changes to
your repo and **refresh the app page**. You could also work locally by using any basic development server, but this is
explained in the [Reference](#reference) section.

## Creating the itemlist

We will finally create the itemlist and add a few items to it. The items will be text only.
In the next section we will add images and show how to render arbitrary HTML.

**Step 1**: Since a repository can contain multiple itemlists, it is a good idea to group into a common folder.
Create a folder named `lists` into the root of your repo.

**Step 2**: Inside the `lists` folder, create the folder in which the itemlist will reside.
I will just name it `itemlist-1`.

**Step 3**: We need to add the itemlist folder to `index.json`. Modify `index.json` like this:
```json
{
	"lists": [
		"lists/itemlist-1"
	]
}
```

**Step 4**: Inside `lists/itemlist-1`, create a `manifest.json` file and add the following text to it:
```json
{
	"title": "Itemlist 1"
}
```
You can replace `Itemlist 1` with an appropriate title for your itemlist.

**Step 5**: Inside `lists/itemlist-1`, create a `data.json` file and add the following text to it:
```json
{
	"items": [
		{
			"name": "Item 1"
		},
		{
			"name": "Item 2"
		},
		{
			"name": "Item 3"
		}
	]
}
```

Push the changes to the repo and refresh the app page. You should see that the index page now contains a link to your
`Itemlist 1`. We will show how to make this page look prettier in the [Reference](#reference) section. For now, click
the link to go to the itemlist page. You should see that it shows 3 items at the bottom the page,
their names corresponding to the `name` properties used in `data.json`. Click the blue **Start** button at the top
of the page to start sorting.

# Reference
