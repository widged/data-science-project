```topic
slug: Dash
tag: +python +react interactive
allies:
status: author-eyes-only
```

[Official Website](https://plot.ly/products/dash/) | [GitHub](https://github.com/plotly/dash/) | [PyPI](https://pypi.python.org/pypi/dash) | [Awesome](https://github.com/Acrotrend/awesome-dash)

# Dash

```scrap
source: https://hackernoon.com/top-10-python-web-frameworks-to-learn-in-2018-b2ebab969d1a
```

GitHub Stars: 3,903 | GitHub Forks: 360

Dash is an open-source Python framework used for building analytical web applications. It’s especially good for Python data scientists who aren’t very familiar with web development.

Dash applications are web servers that run [Flask](http://flask.pocoo.org/) and communicate with JSON packets over HTTP requests. Their frontend renders components with [React.js.](https://reactjs.org/)

Apps developed with Dash are rendered in the web browser and can be deployed to servers. This also means that Dash applications are inherently cross-platform and mobile-ready.

Dash developers have access to the underlying Flask instance and all of its configurable properties. To extend the capabilities of Dash applications, developers can also use the rich set of [Flask Plugins.](http://flask.pocoo.org/extensions/)

## Dash Installation

```scrap
source: https://dash.plot.ly/installation
```

In your terminal, install several dash libraries. These libraries are under active development, so install and upgrade frequently. Python 2 and 3 are supported.

```
pip install dash==0.29.0  # The core dash backend
pip install dash-html-components==0.13.2  # HTML components
pip install dash-core-components==0.38.0  # Supercharged components
pip install dash-table==3.1.5  # Interactive DataTable component (new!)
Ready? Now, let's make your first Dash app.
```

## Dash for Beginners

```scrap
source: https://www.datacamp.com/community/tutorials/learn-build-dash-python
author: [Derrick Mwiti](/profile/mwitiderrick)
recentness: 2018-08-16
```

Learn how to build dashboards in Python using Dash.

Dash is Python framework for building web applications. It built on top of Flask, Plotly.js, React and React Js. It enables you to build dashboards using pure Python. Dash is open source, and its apps run on the web browser. In this tutorial, we introduce the reader to Dash fundamentals and assume that they have prior experience with Plotly.

**Dash Installation**

In order to start using Dash, we have to install several packages.

1.  The core dash backend.
2.  Dash front-end
3.  Dash HTML components
4.  Dash core components
5.  Plotly

```
pip install dash==0.21.1
pip install dash-renderer==0.13.0
pip install dash-html-components==0.11.0
pip install dash-core-components==0.23.0
pip install plotly --upgrade
```

**Dash App Layout**

A Dash application is usually composed of two parts. The first part is the layout and describes how the app will look like and the second part describes the interactivity of the application. Dash provides HTML classes that enable us to generate HTML content with Python. To use these classes, we need to import dash_core_components and dash_html_components. You can also create your own custom components using Javascript and React Js.

To kick us off we shall create a file called app.py using our favorite text editor then import these packages.

```
import dash
import dash_core_components as dcc
import dash_html_components as html
```

Just like in Flask we initialize Dash by calling the Dash class of dash. Once that is done we can create the layout for our application. We use the Div class from the dash_html_components to create an HTML Div. We then use the HTML components to generate HTML components such as H1, H2 etc. `dash_html_components` has all HTML tags. In order to create a graph on our layout, we use the Graph class from `dash_core_components.` Graph renders interactive data visualizations using plotly.js. The Graph class expects a figure object with the `data` to be plotted and the `layout` details. Dash also allows you to do stylings such as changing the background color and text color. You can change the background by using the `style` attribute and passing an object with your specific color. In our case, we have defined a color dictionary with the background and text color we would like. Similarly, we can change the layout background using the `plot_bgcolor` attribute.

In HTML the style property is specified using a semicolon, but in Dash, a dictionary is supplied. The keys in the dictionary are camelCased e.g text-align is textAlign. Instead of using classes like in HTML, className is used in Dash.

```
    app = dash.Dash()
    colors = {
        'background': '#111111',
        'text': '#7FDBFF'
    }
    app.layout = html.Div(style={'backgroundColor': colors['background']}, children=[
        html.H1(
            children='Hello Dash',
            style={
                'textAlign': 'center',
                'color': colors['text']
            }
        ),
        html.Div(children='Dash: A web application framework for Python.', style={
            'textAlign': 'center',
            'color': colors['text']
        }),
        dcc.Graph(
            id='Graph1',
            figure={
                'data': [
                    {'x': [1, 2, 3], 'y': [4, 1, 2], 'type': 'bar', 'name': 'SF'},
                    {'x': [1, 2, 3], 'y': [2, 4, 5], 'type': 'bar', 'name': u'Montréal'},
                ],
                'layout': {
                    'plot_bgcolor': colors['background'],
                    'paper_bgcolor': colors['background'],
                    'font': {
                        'color': colors['text']
                    }
                }
            }
        )
    ])
```

In order to view our visualization, we need to run our web server just like in Flask. Remember Dash is built on top of Flask. We also set debug to true to ensure we don't have to keep refreshing the server every time we make some changes

```
    if __name__ == '__main__':
        app.run_server(debug=True)
```

Next, move to the terminal and start the server by typing the code below: `python app.py`

This will start a new web server at [http://127.0.0.1:8050/](http://127.0.0.1:8050/). Head over there and see your newly created dashboard.

![](http://res.cloudinary.com/dyd911kmh/image/upload/f_auto,q_auto:best/v1529701950/plot1_mqzveh.png)

**Generating Scatter Plots**

In order to plot a scatter plot, we import the normal dash components as previously done. We also need to import Plotly `graph_objs` in order to plot the scatter plot. As mentioned previously we use the Div class and Graph components from Dash in order to accomplish this. The Graph component takes a figure object which has the data and the layout description. We plot the scatter plot using `graph_objs` scatter property. In order to make sure the plot is a scatter plot we pass a `mode` attribute and set it as markers. Otherwise, we would have lines on the graph.

```
    import dash
    import dash_core_components as dcc
    import dash_html_components as html
    import pandas as pd
    import plotly.graph_objs as go

    app = dash.Dash()

    df = pd.read_csv(
        'https://gist.githubusercontent.com/chriddyp/' +
        '5d1ea79569ed194d432e56108a04d188/raw/' +
        'a9f9e8076b837d541398e999dcbac2b2826a81f8/'+
        'gdp-life-exp-2007.csv')


    app.layout = html.Div([
        dcc.Graph(
            id='life-exp-vs-gdp',
            figure={
                'data': [
                    go.Scatter(
                        x=df[df['continent'] == i]['gdp per capita'],
                        y=df[df['continent'] == i]['life expectancy'],
                        text=df[df['continent'] == i]['country'],
                        mode='markers',
                        opacity=0.8,
                        marker={
                            'size': 15,
                            'line': {'width': 0.5, 'color': 'white'}
                        },
                        name=i
                    ) for i in df.continent.unique()
                ],
                'layout': go.Layout(
                    xaxis={'type': 'log', 'title': 'GDP Per Capita'},
                    yaxis={'title': 'Life Expectancy'},
                    margin={'l': 40, 'b': 40, 't': 10, 'r': 10},
                    legend={'x': 0, 'y': 1},
                    hovermode='closest'
                )
            }
        )
    ])

    if __name__ == '__main__':
        app.run_server()
```

![](http://res.cloudinary.com/dyd911kmh/image/upload/f_auto,q_auto:best/v1529701951/plot2_ilbgkm.png)

**Markdown**

Sometimes you may need to include a lot of text in your dashboards. You can do this using dash_core_components `Mardown` attribute as shown below.

```
    import dash
    import dash_core_components as dcc
    import dash_html_components as html

    app = dash.Dash()

    markdown_text = '''
    ### Dash and Markdown
    A lot of text
    '''

    app.layout = html.Div([
        dcc.Markdown(children=markdown_text)
    ])

    if __name__ == '__main__':
        app.run_server()
```

**Core Components**

Next, let's look at some `dash_core_components` that you will encounter when using Dash. You can generate a drop down as shown below. You do by calling `Dropdown` off `dash_core_components` and passing the options as a list of dictionaries. You can set the default value using the `values` attribute and passing in the default option.

```
     dcc.Dropdown(
            options=[
                {'label': 'New York City', 'value': 'NYC'},
                {'label': u'Montréal', 'value': 'MTL'},
                {'label': 'San Francisco', 'value': 'SF'}
            ],
            value='MTL'
        )
```

Generating a multi-select drop down is similar to above. The only changes are that you set the `multi` attribute to `true` since it is False by default. You can then specify the items you would like to be multi-selected by default by specifying the `values` attribute.

```
       html.Label('Multi-Select Dropdown'),
        dcc.Dropdown(
            options=[
                {'label': 'New York City', 'value': 'NYC'},
                {'label': u'Montréal', 'value': 'MTL'},
                {'label': 'San Francisco', 'value': 'SF'}
            ],
            value=['MTL', 'SF'],
            multi=True
        )
```

Radio buttons can be generated using the `RadioItems` attribute. You then pass the options as a list of dictionaries. You can also set a default value by specifying the `values` attribute.

```
    html.Label('Radio Items'),
        dcc.RadioItems(
            options=[
                {'label': 'New York City', 'value': 'NYC'},
                {'label': u'Montréal', 'value': 'MTL'},
                {'label': 'San Francisco', 'value': 'SF'}
            ],
            value='MTL'
        )
```

To generate checkboxes, you call the `Checklist` attribute off `dash_core_components`. The options and default values are passed as above

```
     html.Label('Checkboxes'),
        dcc.Checklist(
            options=[
                {'label': 'New York City', 'value': 'NYC'},
                {'label': u'Montréal', 'value': 'MTL'},
                {'label': 'San Francisco', 'value': 'SF'}
            ],
            values=['MTL', 'SF']
        )
```

You will most certainly need input texts in your application. To generate them you will use the `Input` attribute. Using the Html Label tag, you can create a label for the Input filed. Using the `values` attribute you can specify some text in the field and to specify the type of use `type` and indicate whether its a text field, number, etc.

```
    html.Label('Text Box'),
        dcc.Input(value='MTL', type='text')
```

![](http://res.cloudinary.com/dyd911kmh/image/upload/f_auto,q_auto:best/v1529701951/plot3_pdytlm.png)

**Calling help**

Since Dash components are declarative, calling the help command on any of them will generate the help for that component.

```
help(dcc.Input)
```

### Interactivity

Now let's cover how we can make our Dash apps interactive. In order to do this, we need to import Input and Output from `dash.dependencies`. Don't confuse these with the HTML Input because they are different. The HTML Input is imported from the dash core components. Below we create an input text and bind it a callback such that whenever you type something into that box, it updates `my-div` in real time. In order to enable this Dash provides a decorator `@app` which makes it possible to bind a callback function to `my-div` and the HTML input field. Notice that we use the decorator before we declare the `update_output_div` function.

```python
    import dash
    import dash_core_components as dcc
    import dash_html_components as html
    from dash.dependencies import Input, Output

    app = dash.Dash()

    app.layout = html.Div([
        dcc.Input(id='my-id', value='Dash App', type='text'),
        html.Div(id='my-div')
    ])


    @app.callback(
        Output(component_id='my-div', component_property='children'),
        [Input(component_id='my-id', component_property='value')]
    )
    def update_output_div(input_value):
        return 'You\'ve entered "{}"'.format(input_value)


    if __name__ == '__main__':
        app.run_server()
```

## [Authentication](https://dash.plot.ly/authentication)

Dash provides authentication through a separate package called `dash-auth`. It provides two modes of authentication HTTP Basic Auth and Plotly OAuth. In Basic Auth, you hardcode a set of usernames and passwords in your application. This method has some challenges such as users cannot log out of your application, users cannot create accounts or change passwords, and you are responsible for safely storing the usernames and passwords in your code. Plotly OAuth provides authentication through your online Plotly account, and it's not free.

To set up the Basic Auth proceed as follows. First, install the necessary packages.

```
pip install dash==0.21.1
pip install dash-auth==1.0.0
```

After this set the username and password pairs you would like to have in your application.

```
VALID_USERNAME_PASSWORD_PAIRS = [
    ['hello', 'world']
]
```

The `dash_auth.BasicAuth` utility from Dash will take care of authentication for you once the password pairs have been set. All you have to do is pass the password pairs and your application name to `dash_auth.BasicAuth`.

```
app = dash.Dash('auth')
auth = dash_auth.BasicAuth(
    app,
    VALID_USERNAME_PASSWORD_PAIRS
)
```

![](http://res.cloudinary.com/dyd911kmh/image/upload/f_auto,q_auto:best/v1529702443/plot4_r2273f.png)

## Hosting Dashboards on Heroku

Hosting your dashboard on Heroku is fairly easy but will take a couple of steps.

First, create a directory that will hold all your projects files. You can do this on Ubuntu using the `mkdir` command.

```
$ mkdir my_dash_app
$ cd my_dash_app
```

Next, initialize the folder with git and virtualenv. Git is for version control, and virtualenv will enable us to create a virtual environment to hold all our Python dependencies. After creating the environment, we activate it using the `source` command.

```
$ git init
$ virtualenv venv
$ source venv/bin/activate
```

Next, we install all the packages we need for our Dash application:

```
$ pip install dash
$ pip install dash-renderer
$ pip install dash-core-components
$ pip install dash-html-components
$ pip install plotly
```

In order to serve our Dash application, we need a Python web server. We never use Flask's development server in production. We use `Gunicorn` web server for this function. Install it as shown below:

```
$ pip install gunicorn
```

Next, we need to create a few files in our folder:

1.  app.py where we will code our dash application.
2.  A .gitignore to make sure that unnecessary files are not pushed to production
3.  A requirements.txt file that will contain all the Python dependencies and their versions.
4.  A Procfile for deployment.

Add the following to app.py. This is just an example so you can use your own Dash dashboard.

```
    import os
    import dash
    import dash_core_components as dcc
    import dash_html_components as html
    app = dash.Dash(__name__)
    server = app.server
    app.layout = html.Div([
        html.H2('Hello World'),
        dcc.Dropdown(
            id='dropdown',
            options=[{'label': i, 'value': i} for i in ['LA', 'NYC', 'MTL']],
            value='LA'
        ),
        html.Div(id='display-value')
    ])
    @app.callback(dash.dependencies.Output('display-value', 'children'),
                  [dash.dependencies.Input('dropdown', 'value')])
    def display_value(value):
        return 'You have selected "{}"'.format(value)
    if __name__ == '__main__':
        app.run_server(debug=True)
```

It is important to remind ourselves that at its core a Dash application is also a Flask application. For purposes of deployment, we need to access the Flask application instance. Dash enables us to do this using `app.server`

```
    app = dash.Dash(__name__)
    server = app.server
```

Add the files you would not like to be pushed to production in the .gitignore file. A good Python .gitignore file is available at [Github](https://github.com/github/gitignore/blob/master/Python.gitignore)

Now let's specify our deployment information in the Procfile. We use the web variable to specify our server as gunicorn. We also specify our app details utilizing the app variable. app refers to the filename app.py and server refers to the server variable inside that file.

```
web: gunicorn app:server
```

We also need to write our Python dependencies to the requirements file. Heroku will install them during deployment.

```
pip freeze > requirements.txt
```

The next steps assume that you have an Heroku account and have installed the Heroku CLI. In case you do not have those in place head over to [https://www.heroku.com](https://www.heroku.com) and set them up.

The next step is to create a Heroku app on the terminal and add all our application packages. Once you have committed the changes; push your application to heroku master. The output of this command will have a link to your live Dash application on Heroku.

```
    $ heroku create your-app-name
    $ git add .
    $ git commit -m 'Your-commit-message'
    $ git push heroku master
```

This serves as an introduction to building a dashboard in pure Python using Dash by Plotly. To learn more about Dash visit the official [docs](https://dash.plot.ly).

If you are interested in learning more about python, check out our [Intermediate Python for Data Science](https://www.datacamp.com/courses/intermediate-python-for-data-science) course.

## Docs

https://github.com/plotly/dash-docs

## Encapuslating D3.js Charts as Python Dash Components

```scrap
source: https://dash.plot.ly/d3-react-components
```

D3.js is a flexible library for rendering and animating SVG in the web browser. It's approach toward rendering content in the DOM is quite different than React.js, the user interface library that Dash components use.

By popular demand, we've created a set of tutorials to help you make high quality Dash components with D3.js. Beyond D3, these tutorials should also help you better understand how to integrate 3rd-party libraries into your custom React and Dash components.

- Tutorial 1 - [React + D3.js, Guiding Principles](https://gist.github.com/alexcjohnson/a4b714eee8afd2123ee00cb5b3278a5f)
- Tutorial 2 - [Real World Example: Dash Sunburst](https://github.com/plotly/dash-sunburst)
- Tutorial 3 - [Real World Example: Dash Network](https://github.com/plotly/dash-network)

Questions or feedback? Let us know in our [Dash + D3 Feedback Thread](https://github.com/plotly/dash-docs/issues/242)

> Note: Before you dig in too deep into D3.js, we recommend checking out [`plotly.js`](https://github.com/plotly/plotly.js), our flagship open source charting library. Since 2012, we've worked hard to abstract away the complexity of data visualization through a standard, declarative interface for over 30 chart types. Under the hood, `plotly.js` uses D3.js and WebGL. `dash_core_components.Graph` is the official Dash interface to `plotly.js`.

---

[](/)Back to the Table of Contents

## Extras

https://github.com/plotly/dash-table-experiments

https://dash.plot.ly/authentication

https://github.com/plotly/dash-redis-demo

## Bookmarks

https://pypi.org/project/dash.py/

# Dash Projects

You can find below the list of the Dash Apps and Components I created.

## Apps

**t-SNE Explorer**:
[Link to Repo](https://github.com/plotly/dash-tsne) | [Demo App](https://dash-tsne.plot.ly/)

**SVM Explorer**:
[Link to Repo](https://github.com/plotly/dash-svm) | [Demo App](http://dash-svm.herokuapp.com/)

**Image Processing App**:
[Link to Repo](https://github.com/plotly/dash-image-processing) | [Demo App](http://dash-image-processing.herokuapp.com/)

**Live Model Training Viewer**:
[Link to Repo](https://github.com/plotly/dash-live-model-training) | [Demo App](https://dash-live-model-training.plot.ly/)

**Object Detection App**:
[Link to Repo](https://github.com/plotly/dash-object-detection) | [Demo App](https://dash-object-detection.plot.ly/)

**Regression Explorer**:
[Link to Repo](https://github.com/plotly/dash-regression) | [Demo App](https://dash-regression.herokuapp.com/)

## Components

### Writing

# Writing your own components

```scrap
https://dash.plot.ly/plugins
```

One of the really cool things about dash is that it is built on top of [React.js](https://facebook.github.io/react/), a JavaScript library for building web components.

The React community is huge. Thousands of components have been built and released with open source licenses. For example, here are just some of the [slider components](https://react.rocks/?q=slider) and [table components](https://react.rocks/?q=tables) that have been published by the React community, any of which could be adapted into a Dash Component.

## Creating a Component

To create a Dash component, fork our sample component repository and follow the instructions in the README.md: [https://github.com/plotly/dash-component-boilerplate](https://github.com/plotly/dash-component-boilerplate)

If you are just getting started with React.js as a Python programmer, please check out our essay ["React for Python Devs"](https://dash.plot.ly/react-for-python-developers).

### How Are Components Converted From React.js to Python?

Dash provides a framework that converts React components (written in JavaScript) into Python classes that are compatible with the Dash ecosystem.

On a high level, this is how that works:

- Components in dash are serialized as [JSON](www.json.org). To write a dash-compatible component, all of the props shared between the Python code and the React code must be serializable as JSON. Numbers, Strings, Booleans, or Arrays or Objects containing Numbers, Strings, Booleans. For example, JavaScript functions are not valid input arguments. In fact, if you try to add a function as a prop to your Dash component, you will see that the generated Python code for your component will not include that prop as part of your component's accepted list of props. (It's not going to be listed in the `Keyword arguments` enumeration or in the `self._prop_names` array of the generated Python file for your component).
- By annotating components with React docstrings (not required but helpful and encouraged), Dash extracts the information about the component's name, properties, and description through [React Docgen](https://github.com/reactjs/react-docgen). This is exported as a JSON file (metadata.json).
- At build time, Dash reads this JSON file and dynamically creates Python classes that subclass a core Dash component. These classes include argument validation, Python docstrings, types, and a basic set of methods. _These classes are generated entirely automatically._ A JavaScript developer does not need to write _any_ Python in order to generate a component that can be used in the Dash ecosystem.
- You will find all of the auto-generated files from the build process in the folder named after your component. When you create your Python package, by default any non-Python files won't be included in the actual package. To include these files in the package, you must list them explicitly in `MANIFEST.in`. That is, `MANIFEST.in` needs to contain each JavaScript, JSON, and CSS file that you have included in your `my_dash_component/` folder. In the `dash-component-boilerplate` repository, you can see that all the javascript for your React component is included in the build.js file.
- The Dash app will crawl through the app's `layout` property and check which component packages are included in the layout and it will extract that component's necessary JavaScript or CSS bundles. Dash will serve these bundles to Dash's front-end. These JavaScript bundles are used to render the components.
- Dash's `layout` is serialized as JSON and served to Dash's front-end. This `layout` is recursively rendered with these JavaScript bundles and React.

### Boilerplate

https://github.com/plotly/dash-component-boilerplate

### Available

[**Dash Player**](https://github.com/xhlulu/dash-player) - Dash Player is a dash component for playing a variety of URLs, including file paths, YouTube, Facebook, Twitch, SoundCloud, Streamable, Vimeo, Wistia, Mixcloud, and DailyMotion. It is wrapped around the react-player component.

[**Dash Webcam**](https://github.com/xhlulu/dash-webcam) - Dash Component wrapping React-Webcam

[**Dash Katex**](https://github.com/xhlulu/dash-katex) - Katex.js in Python using Dash

[**Dash Draggable**](https://github.com/xhlulu/dash-draggable) - react-draggable in Python

## Repos

[github/xhlulu](https://github.com/xhlulu?tab=repositories&q=dash&type=&language=)

## Screenshots

### t-SNE Explorer

![tsne](https://raw.githubusercontent.com/xhlulu/dash-projects/master/images/tsne.gif)

### Live Model Training Viewer

![live-model-training](https://raw.githubusercontent.com/xhlulu/dash-projects/master/mages/live-model-training.gif)

### Object Detection App

![object-detection](https://raw.githubusercontent.com/xhlulu/dash-projects/master/images/object-detection.gif)

### Image Processing App

![image-processing](https://raw.githubusercontent.com/xhlulu/dash-projects/master/images/image-processing.gif)

### SVM Explorer

![svm](https://raw.githubusercontent.com/xhlulu/dash-projects/master/images/svm.gif)

### Regression Explorer

![regression](images/regression.gif)
