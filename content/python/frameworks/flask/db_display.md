---
Title: 'How to display data from your database with Flask/jinja'
Subjects:
  - 'Python'
  - 'Computer Science'
  - 'Flask'
  - 'Jinja'
---

## What is Jinja
So you want to display some of that b-e-a-utiful data you've got but are too stubborn to do it with a front-end frame work. That's what's up. We'll kick JavaScript to the curb and use Jinja. 

'Jinja!? is that an Australian Red Head?' you may ask...

well, yeah maybe...

But also!

Its this [spicy little guy](https://jinja.palletsprojects.com/en/3.1.x/). Jinja lets us inject python code and functionality into html.

In this case it gives us the power to loop through data from our database and cleanly display it on our webpage. And that is pretty neat.

## Getting Started
If you've made it this far we're going to assume you've gotten your database connected. We can also assume that your models have been sent off and are frolicking happily in the cloud somewhere. 

The first thing you'll need is an html page, which again if you've made it this far you likely already have. Good work!
This will represent our hypothetical index.html

### Hello it me, the index.html. Let's go inside me (*￣3￣)╭

*schloop*

We'll create a div and throw a table in there (╯‵□′)╯︵┻━┻

<div>

    <table>
    <tr>
        <th></th>
        <th></th>
        <th></th>
        <th></th>
    </tr>
    <tr>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>

    </table>
</div>


Super Duper, next all we need is a route to render that sweet, sweet html page.


```py
@site.route('/')
def really_cool_homepage():    
   
    return render_template('index.html')


```

Neat, that'll do it. Our table is ready to display our data and the route is super routey.


## Querying Our DB and Displaying Data in HTML

All that's left is to add some functionality to our route. We're going to query our db table and store that data into a variable, then send it off to our html via the render template.

Gotta catch em all!
Hopefully this isn't any kind of infringement, I just really like pokemon.

Let's pretend we have a table called Pokemon.
Here is our hypothetical models.py

```py
class Pokemon(db.Model):
    name = db.Column(db.String)
    type_ = db.Column(db.String(150), nullable = True, default = '')
    is_it_cool = db.Column(db.Boolean, nullable = True, default = '')
    generation = db.Column(db.String(150), nullable = False)
   
    
    
```
Now let's query the pokemon table from our db. We can do this by referencing our pokemon model. 
```py
import Pokemon from .models #make sure to import your model if needed, we will reference this for your query.
@site.route('/')
def really_cool_homepage():

    pokemon = Pokemon.query.all() # This will assign all Pokemon data to a variable we can pass into the render template

    # pokemon = Pokemon.query.filter_by(filter criterua here).all()  
    # You can also use filter_by to display more specific data.
    # For example, you can fileter to query all pokemon associated with one user.
   


    return render_template('index.html' pokemon = pokemon) # pass our pokemon variable through the render_template so jinja knows what its looping through in the HTML.

```

SO YOU WANNA BE A MASTER OF 
POKEMON
DO YOU HAVE THE SKILS TO BE
NUMBER ONE!?

we'll see. Now back to the html to bring in the Jinja 
(☞ﾟヮﾟ)☞

Now we can fill in our column headers in with info from our Pokemon Model. 

Then we will use jinja to loop through the data we stored in our pokemon variable. 
We have access to that bad boy because when our render_template gets returned, the data is passed with it. 
Thanks render_template!

We will start our jinja statement just below the table tag and end it just above the closing table tag.
This is because when it loops it will populate a row for each piece of data in our db. We don't want a thousand-something tables or whatever your pokedex is at, but we do want that many rows.

Finally we can access the data from our table with the names of the columns we created in our model.
In our case we insert poke.name, poke.type_, poke.is_it_cool, and poke.generation into the td elements below.

DONT FORGET YOUR {% ENDFOR %}
Anytime you start a statement in Jinja, it also needs to be closed out, lest you be scolded by the debugger.

<div>

    <table>

    {% for poke in pokemon%}
    <tr>
        <th>Name</th>
        <th>Type</th>
        <th>Is It Cool?</th>
        <th>Generation</th>
    </tr>
    <tr>
        <td>poke.name</td>
        <td>poke.type_</td>
        <td>poke.is_it_cool</td>
        <td>poke.generation</td>
    </tr>

    {% endfor %}

    </table>
</div>

## Conclusion
Jinja is cool. You should have some nicely displayed data, probably pending some CSS but that is a tale for another tame. Great work out there. Now go stretch and drink some water!

So long, and thanks for all the fish!







