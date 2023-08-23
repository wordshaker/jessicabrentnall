
## Jessica Brentnall's Personal Website

The personal website of Jessica Brentnall.

## Development Instructions
---
### Building Locally

To build the project locally

~~~bash
$ cd ./site
$ cd bundle exec jekyll build
~~~

## Running Locally

Install the dependencies:

~~~bash
$ npm run install-jekyll
~~~

Run the website:

~~~bash
$ npm start
~~~

You may need to run these commands first 

~~~bash
$ npm install
$ bundle install
~~~

## Gotchas
----
- When running locally, you will only see posts that are in the past or dated for the current day.
- Sometimes the `.html`'s are not automatically removed from urls, breaking the websites paths post deployment

## Deployment pipeline
---
GitHub Actions is set up to build on pull request. When a pull request is merged into main, the site will be deployed through github actions

## Jekyll Template Used
---
Vonge is a Personal portfolio/blog site template for Jekyll. Browse through a [live demo](https://jazzed-kale.cloudvent.net/).
Increase the web presence of your brand with this configurable theme.

Vonge was made by [CloudCannon](http://cloudcannon.com/), the JAMStack Cloud CMS.
The component library is built and maintained for use with [Bookshop](https://github.com/cloudcannon/bookshop/)