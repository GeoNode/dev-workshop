# GeoNode Workshops

## How to run the presentation locally

### Prerequisites

Install [Compass](http://compass-style.org/install/) to compile graphic themes:

```bash
$ gem update --system
$ gem install compass
```

Make sure Compass has been successfully installed. On Ubuntu machines you may need some system packages in order to install it

```bash
$ sudo apt-get install ruby-dev
```

### Live presentation dependencies

Install dependencies with [npm](https://www.npmjs.com/) and [bower](https://bower.io/):

```bash
$ npm install
```

and

```bash
$ bower install
```

Serve it locally:

```bash
$ grunt serve
```

Open the browser at [http://localhost:9000](http://localhost:9000)

## How to add new slides

Add a new slide `my-new-slide.md` as a new [Markdown](https://en.wikipedia.org/wiki/Markdown) file under the directory `slides` and use its syntax to create the content of that page.

The new file has to be listed as a new item in the JSON file `list.json`:

```json
    {
        "filename": "my-new-slide.md",
        "attr": {
            "data-background": "css/img/bg.png"
        }
    },
```

Change the `data-background` if you want to change the background image.

## How to publish online

Open the gruntfile configuration `Gruntfile.coffee` and change the directory for publishing the current workshop in the `dest` properties:

```coffee
copy:

            dist:
                files: [{
                    expand: true
                    src: [
                        'slides/**'
                        'bower_components/**'
                        'js/**'
                        'css/*.css'
                        'resources/**'
                        'css/img/**'
                        'css/fonts/**'
                    ]
                    dest: 'dist'
                },{
                    expand: true
                    src: ['index.html']
                    dest: 'dist'
                    filter: 'isFile'
                }]
```

Run then the build with the command:

```bash
$ grunt dist
```

Deploy on specific folder of github pages:

```bash
$ grunt deploy
```

## Data

Data are distributed within an archive in a directory `data` together the presentation and this folder can be also mounted into the virtual machine if required.
