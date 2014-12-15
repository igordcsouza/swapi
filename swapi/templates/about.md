## What is this?

The Star Wars API is the world's first quanitified and organised data set of Star Wars data ever created.

After hours of watching films and trawling through content online, we present to you all the **People, Films, Species, Starships, Vehicles and Planets** from Star Wars.

We've formatted this data in **JSON** and exposed it to you in a **RESTish** implementation that allows you to programmatically collect and measure the data.

[Check out the documentation to get started consuming swapi data](/documentation)

## What can you use this for?

Comparing the data from Star Wars has never been easier. Here are some examples using the [Python helper library](/documentation#python_helper)

*List the planets in order of size*:


    import swapi
    for planet in swapi.get_all("planets").order_by("diameter"):
        print planet.name


*View the people who have piloted more than one starship*:

    import swapi
    for people in swapi.get_all("people"):
        if len(people.starships) > 1:
            print people.name

*Discover if Jar Jar Binks ruined a film just by being in it*:

    import swapi
    pm = swapi.get_film(episode_id=1)
    jj = swapi.get_person(name="Jar Jar Binks")
    if jj.id in pm.characters:
        print "Why George, why."

## Why did you build this?

I built the [Pokémon API](http://pokeapi.co) before I built this. I realised that *if you provide data easily, someone will consume it*. I got bored around Christmas 2014 and decided that I'd take what I learned from PokéAPI and build an API for Star Wars data.

Seeing the release trailer for Episode VII also made me stupidly enthusiastic for Star Wars again.

## Who are you?

I'm [Paul Hallett](http://phalt.co), an *"API engineer"* who is also super nerdy. I want a job building amazing APIs, [get in touch if you want to hire me.](mailto:paulandrewhallett@gmail.com)