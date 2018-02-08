# WADE

Welcome to the WAter Data Exchange (WADE). This is intended to be a system for citizen science water observation publishing. This Data Exchange relies upon the connections between groups' repositories, so in order to participate, you will need to "fork" this repository.Not sure what the means? We explain below!

## Introductory Terminology

* Github: A website that makes contributing data and software easier. Github is commonly used for a large number of open-source software and data projects.
* Git: Git is a software versioning system developed for open-source. It is a system for keeping track of changes in software development, but it works just as well for text and data. For the most part, you shouldn't have to worry about how it works or how to use it.
* Repository: A repository is a collection of data/text. In the context of WADE, a repository is forked from the original `Foundry-Spatial/WADE` repository.  Commonly shortened to "repo".
* Forking a repository: A fork is a copy of a repository. Forking a repository allows you to freely experiment with changes without affecting the original project. Most commonly, forks are used to either propose changes to someone else's project, or to use someone else's project as a starting point for your own idea.
* License: A licence in the context of this repository.

## Participating

This project is designed not only to make contributing easy, but accessing contributions from other groups should be straight-forward as well. If you have any difficulties in navigating the website, please contact Foundry Spatial at technical@foundryspatial.com.

Forking this project will also give you a website page at a URL that looks like this: `https://<username>.github.io/<projectname>/`. For example, this project has a website page here: <https://foundry-spatial.github.io/WADE/>, which was generated from the `index.md` file in the `docs` directory - Modify as you like but please keep the `---` lines at the top of file or your page won't get generated.  [Read more about github pages.](https://pages.github.com/)

### Sign up and sign in to github

If you haven't created an account for github already, please follow their instructions at <https://github.com/join>.  Once you have confirmed your email and account information, please visit [this repository](https://github.com/Foundry-Spatial/WADE) again, or refresh your browser.

### Fork this repo

To fork this repository, click on **Fork** in the top right corner of this page.

### Set up Git

#### Desktop client

The easiest way to use github on Windows/*nix/MacOS is to install the github desktop client. You may find this at <https://desktop.github.com/>

#### CLI

You may also want to use the native git client - to do so, follow the instructions at <https://git-scm.com/book/en/v1/Getting-Started-Installing-Git>

You will need to "clone" your newly created repository (which should be located somewhere like `https://github.com/<yourname>/WADE`).

This will put a copy of the repository on your local system, which you may then add to or edit.

Once you have finished editing, add any changed files, and commit. You will then need to "push" your changes to github.

## Data Format

Water data can naturally be divided into two components:

1. information on the location where it is collected - location name, coordinates, type of feature, instrument used, etc…
1. associated with specific monitoring events, include the date, time, parameter measured, detection limit, units, and measured value.

Simple (yet extendable) data elements are included in the `data` folder. You may extend the data as required as long as these basic data characteristics are maintained.

### Required files

#### data/meta.csv

This file contains any "metadata" you wish to have for the system. This may include but is not limited to: `group name`, `group contributors`, `contact email`, &c. Please modify the `meta.csv` file to reflect your working group's information, and add any other data as required.

#### data/locations.csv

This file contains unique station/location ids, and their corresponding names, as well as their geospacial location, either as a point (latitude, longitude values) or alternatively a geojson shape.

#### data/<>.csv

All other files in the `data` directory will be considered as "observational data". In other words, you may separate out your CSV in whichever way you choose, as long as it makes sense to you. However, there needs to be the following columns for any of these files:

* location id, which *must* correspond to a location ID, and be unique (i.e. don't use the same id twice)
* date or datetime (with time zone, if possible) in [ISO 8601 standard format](https://en.wikipedia.org/wiki/ISO_8601) - e.g. `2007-03-01T13:00:00Z`, `2017-12-31`

All headers in the observational data csvs should include the variable and their measurement units as required. e.g. Stream Discharge (m3/s), Water Level (Metres), Minimum Temperature (celsius), &c.  See the example `observations.csv` file.  You may edit this file or add others.

