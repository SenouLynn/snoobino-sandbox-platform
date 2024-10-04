# Sandbox

Flesh out architecture minutia without consideration for production deployments

## Core Product Goals

Public: Build an application where any user can view details about a [model]
Private: Build a user system where users can interact with a [model] and attribute [feature-data] to a given [model]

## Desired Features

### Model Specification

#### Static

Description: The core model definitions that make up the 'thing' 

- Name
- Date Created
- Description
- Image(s)
- ???

### Dynamic (attributed by users)

Description: How users will interact with the model

- Rating
- Comments
- Tags (categorical - the 'vibe')
- ???

### Internal Aggregation of Dynamic Content

Description: this data will incidentally become available once dynamic attributions begin to take shape

- Average rating
- Number of comments
- General vibe yo
- ???

## Core Architecture Considerations

### Front-End - UI Layer

FrontPrimary goal seems to be getting onto the app store - this likely means leaning into react-native (ultimately). It's important to note that UI libraries built for the web are not compatible with native libraries as the code is run on fundamentally different systems. Seems like native tooling also doesn't technically run css like browsers do but exposes css-like syntax.

#### Front-End Tools to Explore

- React-native-web - library that allows you to react-native components on the React-DOM allowing you to test in the browser.
- NativeWind - Tailwind for react-native. Hell yeah.


### Front-end - BFF Layer

BFF likely won't be necessary if we are able to use `react-query` to good effect - TRPC may be overkill for the simplicity of the data model (right now)

### Backend Server

Node may be common ground here. Both Brandon and I can write javascript and could be a good place to start. This shouldn't be the end goal though. Python would be my next exploratory recommendation however I believe GO-Lang would be best in the long run.

#### GoLang Tools to Explore

- Gin - Beginner-friendly REST framework
- Echo - Minimalist REST framework - loosely based on Express

### Database Interaction Layer

This is where my knowledge largely falls off. I've got some experience in Javascript interacting with a local SQLite db to good effect. We may want to start here at the top of the stack so we can ignore the backend entirely and focus on front-end state management then port the model definitions to the backend of choice.

### Production Build Tooling + Deployment Pipeline

If we get to this point, we'll have to pull in some heavy guns.


## Tools

### Create a Directory (shorthand)

```
turbo gen workspace
```