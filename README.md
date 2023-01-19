# Overview

This should serve as a tutorial on how to create itemlists for
[Fansort](https://floofnoodlecode.github.io/fansort/#/title?EOL=), an item sorter for user-defined itemlists.

This repository is also an itemlist collection that demonstrates all the features that you can use
for your custom itemlists. In order to see these features you can go to
https://floofnoodlecode.github.io/fansort/#/index/m8Q0jWF9Wk5-flpefn5KTmpyfkoq45q0xLzi_KIS3ZTU3HymJbmJmXkA?EOL=
to view the results.

Contents:
1. [Quickstart](#quickstart) - Teaches you the minimal information you need to know to create itemlists
2. [Advanced](#advanced) - Explains all the features that an itemlist can make use of

# Quickstart

This section will guide you through the process of creating a minimal itemlist from scratch. See the [Advanced](#advanced) section for in-depth detail of all the features.

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
explained in the [Advanced](#advanced) section.

## Creating the itemlist

We will finally create the itemlist and add a few items to it. The items will be text only.
In the next section we will add thumbnails for our items.

**Step 1**: Since a repository can contain multiple itemlists, it is a good idea to group into a common folder.
Create a folder named `lists` into the root of your repo.

**Step 2**: Inside the `lists` folder, create the folder in which the itemlist will reside.
I will just name it `programming-languages`.

**Step 3**: We need to add the itemlist folder to `index.json`. Modify `index.json` like this:
```json
{
	"lists": [
		"lists/programming-languages"
	]
}
```

**Step 4**: Inside `lists/programming-languages`, create a `manifest.json` file and add the following text to it:
```json
{
	"title": "Programming Languages"
}
```
`title` property is used as the default title for a new itemlist.

**Step 5**: Inside `lists/programming-languages`, create a `data.json` file and add the following text to it:
```json
{
	"items": [
		{
			"name": "Python"
		},
		{
			"name": "Javascript"
		},
		{
			"name": "Typescript"
		}
	]
}
```

Push the changes to the repo and refresh the app page. You should see that the index page now contains a link to your
`Programming Languages`. We will show how to make this page look prettier in the [Advanced](#advanced) section. For now, click
the link to go to the itemlist page. You should see that it shows 3 items at the bottom the page,
their names corresponding to the `name` properties used in `data.json`. Click the blue **Start** button at the top
of the page to start sorting.

## Item thumbnails

First, let's download some images and put them in the itemlist folder. The path doesn't matter. You can find the images
in the `assets/` folder. Next, the `data.json` needs to be updated to specify the image corresponding to each item:
```json
{
	"items": [
		{
			"name": "Python",
			"props": {
				"img": "assets/python.png"
			}
		},
		{
			"name": "Javascript",
			"props": {
				"img": "assets/javascript.png"
			}
		},
		{
			"name": "Typescript",
			"props": {
				"img": "assets/typescript.png"
			}
		}
	]
}
```

The `props` property is used to specify arbitrary data for each item. This data will be available in the
[LiquidJS](https://liquidjs.com/index.html) template that we will create next.

Add a folder named `liquid` in the `lists/programming-languages` folder.
In this folder, create a `thumb.liquid` file and add the following text to it:
```xml
<image src="{{item.props.img}}" width="62" height="62"/>
```

The app renders this template for each item. The template will receive an `item` variable which contains the JSON object
corresponding to that item. Notice how the template uses `{{item.props.img}}` to decide the `src` dynamically.

Note that the rendered `thumb.liquid` is interpreted as an XML specific to Fansort.
In this case the `<image>` tag instructs the app to render the image given in `src`.
`width` and `height` specify the final width and height of the image, but they are optional.
More details in [Advanced](#advanced).

# Advanced
