# GRANDstack Zillow Clone

This project uses [GRANDstack Start](https://github.com/grand-stack/grand-stack-starter) to build a [GRANDstack](https://grandstack.io) (GraphQL, React, Apollo, Neo4j Database) Zilow clone.

This project was coded along with the [Building A Real Estate Search App with GRANDstack](https://www.youtube.com/playlist?list=PL9Hl4pk2FsvUjfSsxLolVToO5t1hwEIKK) playlist

## Data Model

<details>
  <summary>Arrows markup</summary>
  
  Markup for defining data model using the [Arrows graph diagraming tool](http://www.apcjones.com/arrows/)

```html
<ul
  class="graph-diagram-markup"
  data-internal-scale="1"
  data-external-scale="1"
>
  <li
    class="node"
    data-node-id="0"
    data-x="-1713.637451171875"
    data-y="317.54315185546875"
  >
    <span class="caption">User</span>
    <dl class="properties">
      <dt>id</dt>
      <dd>String</dd>
      <dt>name</dt>
      <dd>String</dd>
    </dl>
  </li>
  <li
    class="node"
    data-node-id="1"
    data-x="-729.3491363525391"
    data-y="1243.0390625"
  >
    <span class="caption">Listing</span>
    <dl class="properties">
      <dt>createdAt</dt>
      <dd>DateTime</dd>
      <dt>listingId</dt>
      <dd>String</dd>
      <dt>askingPrice</dt>
      <dd>Int</dd>
      <dt>bedRooms</dt>
      <dd>Int</dd>
      <dt>bathRooms</dt>
      <dd>Int</dd>
      <dt>squareFootage</dt>
      <dd>Int</dd>
    </dl>
  </li>
  <li
    class="node"
    data-node-id="2"
    data-x="1083.0440673828125"
    data-y="-459.44090270996094"
  >
    <span class="caption">City</span>
    <dl class="properties">
      <dt>name</dt>
      <dd>String</dd>
    </dl>
  </li>
  <li
    class="node"
    data-node-id="3"
    data-x="28.259565114974976"
    data-y="458.7174263000488"
  >
    <span class="caption">Property</span>
    <dl class="properties">
      <dt>id</dt>
      <dd>String</dd>
      <dt>address</dt>
      <dd>String</dd>
      <dt>location</dt>
      <dd>Point</dd>
      <dt>bounds</dt>
      <dd>[Point]</dd>
    </dl>
  </li>
  <li
    class="node"
    data-node-id="4"
    data-x="1409.7587890625"
    data-y="554.8055877685547"
  >
    <span class="caption">Listing</span>
    <dl class="properties">
      <dt>createdAt</dt>
      <dd>DateTime</dd>
      <dt>active</dt>
      <dd>Bool</dd>
      <dt>askingPrice</dt>
      <dd>Int</dd>
    </dl>
  </li>
  <li
    class="node"
    data-node-id="5"
    data-x="252.71633911132812"
    data-y="-393.4471435546875"
  >
    <span class="caption">Neighborhood</span>
    <dl class="properties">
      <dt>name</dt>
      <dd>String</dd>
    </dl>
  </li>
  <li
    class="node"
    data-node-id="6"
    data-x="-729.3491363525391"
    data-y="-348.6604309082031"
  >
    <span class="caption">Subdivision</span>
    <dl class="properties">
      <dt>name</dt>
      <dd>String</dd>
    </dl>
  </li>
  <li
    class="node"
    data-node-id="7"
    data-x="682.1227416992188"
    data-y="1032.9970703125"
  >
    <span class="caption">Appraisal</span>
    <dl class="properties">
      <dt>property_id</dt>
      <dd>String,</dd>
      <dt>year</dt>
      <dd>Int,</dd>
      <dt>land</dt>
      <dd>Int,</dd>
      <dt>building</dt>
      <dd>Int,</dd>
      <dt>total</dt>
      <dd>Int,</dd>
      <dt>method</dt>
      <dd>String</dd>
    </dl>
  </li>
  <li
    class="node"
    data-node-id="8"
    data-x="28.259565114974976"
    data-y="1112.759033203125"
  >
    <span class="caption">Appraisal</span>
    <dl class="properties">
      <dt>property_id</dt>
      <dd>String,</dd>
      <dt>year</dt>
      <dd>Int,</dd>
      <dt>land</dt>
      <dd>Int,</dd>
      <dt>building</dt>
      <dd>Int,</dd>
      <dt>total</dt>
      <dd>Int,</dd>
      <dt>method</dt>
      <dd>String</dd>
    </dl>
  </li>
  <li class="relationship" data-from="0" data-to="1">
    <span class="type">SAVED</span>
    <dl class="properties">
      <dt>createdAt</dt>
      <dd>DateTime</dd>
    </dl>
  </li>
  <li class="relationship" data-from="1" data-to="3">
    <span class="type">OF</span>
  </li>
  <li class="relationship" data-from="4" data-to="3">
    <span class="type">OF</span>
  </li>
  <li class="relationship" data-from="3" data-to="2">
    <span class="type">IN_CITY</span>
  </li>
  <li class="relationship" data-from="3" data-to="5">
    <span class="type">:IN_NEIGHBORHOOD</span>
  </li>
  <li class="relationship" data-from="3" data-to="6">
    <span class="type">:IN_SUBDIVISION</span>
  </li>
  <li class="relationship" data-from="3" data-to="7">
    <span class="type">HAS_APPRAISAL</span>
  </li>
  <li class="relationship" data-from="3" data-to="8">
    <span class="type">HAS_APPRAISAL</span>
  </li>
</ul>
```

</details>

![Graph data model](img/datamodel.svg)


Below you'll find the original [GRANDstack Start](https://github.com/grand-stack/grand-stack-starter) README

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://grandstack.io/deploy-starter-netlify) [![Deploy to Vercel](https://vercel.com/button)](https://grandstack.io/deploy-starter-vercel) [![Provision Neo4j](https://grandstack.io/img/provision-neo4j.png)](https://sandbox.neo4j.com/?usecase=blank-sandbox)

# GRANDstack Starter

```
npx create-grandstack-app myNewApp
```

This project is a starter for building a [GRANDstack](https://grandstack.io) (GraphQL, React, Apollo, Neo4j Database) application. There are two components to the starter, the web frontend application (in React and Angular flavors) and the API app (GraphQL server).

The starter represents a **business reviews dashboard**. You need to adjust the GraphQL schema, the seed data, database index creation, and the UI components for your use-case.

[![Hands On With The GRANDstack Starter](http://img.youtube.com/vi/rPC71lUhK_I/0.jpg)](http://www.youtube.com/watch?v=1JLs166lPcA 'Hands On With The GRANDstack Starter')

_Hands On With The GRANDstack Starter Video_

## Quickstart

The easiest way to get started with the GRANDstack Starter is to create a Neo4j Sandbox instance and use the `create-grandstack-app` command line tool.

(If you have a running Neo4j database on localhost via Neo4j Desktop or a Neo4j server installation, change the password in `api/.env`)

### 1. Create A Neo4j Instance

#### Option :one: - Sandbox

[Neo4j Sandbox](https://neo4j.com/sandbox) allows you to create a free hosted Neo4j instance private to you that can be used for development.

After signing in to Neo4j Sandbox, click the `+ New Project` button and select the "Blank Sandbox" option. In the next step we'll use the connection credentials from the "Connection details" tab to connect our GraphQL API to this Neo4j instance.

![Neo4j Sandbox connection details](img/neo4j-sandbox.png)

#### Option :two: - Desktop

If you instead would like to use [Neo4j Desktop](https://neo4j.com/download/). The process will be almost the same with a minor detour. Install Neo4j Desktop for your chosen OS and then make a new blank graph for your project. It will require you to put in a password and username. Remember those.

Next you need to go to open the manage screen from the options in the 3 dot stack menu

![New desktop graph, manage tab](img/desktop-new-graph.png)

And install the apoc plugin, green button at the top of the list.

![Plugins](img/apoc-install.png)

After that you can return to setting up your app with the credentials from the prior steps.

### 2. Run the `create-grandstack-app` CLI

```
npx create-grandstack-app myNewApp
```

or with Yarn

```
yarn create grandstack-app myNewApp
```

![create grandstack app output](img/create-grandstack-app.png)

This will create a new directory `myNewApp`, download the latest release of the GRANDstack Starter, install dependencies and prompt for your connection credentials for Neo4j to connect to the GraphQL API.

### 3. Seed the database (optional)

Make sure your application is running locally with `npm start` or `yarn start`, open another terminal and run

```
npm run seedDb
```

or with Yarn

```
yarn run seedDb
```

### 4. Open In Browser

![Grandstack app running in browser](img/grandstack-app.png)

## <a name="overview"></a> Overview

The GRANDstack Starter is a monorepo that includes a GraphQL API application and client web applications for React (default) and Angular for a business reviews dashboard.

### `/` - Project Root

The root directory contains some global configuration and scripts:

- `npm run start` and `npm run build`
- ESLint (.eslintrc.json) for code linting
- Prettier (.prettierrc.json) for code formatting
- Git hooks for applying formatting on commit

### [`/api`](./api)

![](img/graphql-playground.png)

This directory contains the GraphQL API application using Apollo Server and the Neo4j GraphQL Library.

- Change environment variable settings in `.env`:

```
# Use this file to set environment variables with credentials and configuration options
# This file is provided as an example and should be replaced with your own values
# You probably don't want to check this into version control!

NEO4J_URI=bolt://localhost:7687
NEO4J_USER=neo4j
NEO4J_PASSWORD=letmein

# Uncomment this line to enable encrypted driver connection for Neo4j
#NEO4J_ENCRYPTED=true

# Uncomment this line to specify a specific Neo4j database (v4.x+ only)
#NEO4J_DATABASE=neo4j

GRAPHQL_SERVER_HOST=0.0.0.0
GRAPHQL_SERVER_PORT=4001
GRAPHQL_SERVER_PATH=/graphql

```

### [`/web-react`](./web-react)

![](img/grandstack-app.png)

The frontend React web application is found in this directory.

It includes:

- Material UI
- React router
- Apollo Client / React Hooks
- Create React App

### [`/web-angular`](./web-angular)

![](web-angular/img/angular-ui.jpg)

A UI built with [Angular](https://angular.io), [Apollo](https://www.apollographql.com/docs/angular/) and the [Clarity Design System](https://clarity.design) is also available.

_Start the Angular UI server_

```
cd ./web-angular && npm start
```

### [`/mobile_client_flutter`](./mobile_client_flutter)

![](img/grandstack-flutter.png)

A mobile client built with [Flutter](https://flutter.dev) which supports Android, iOS, and web. See the [README](./mobile_client_flutter/README.md) for detailed setup instructions.

```
cd ./mobile_client_flutter && flutter run
```

### [`/web-react-ts`](./web-react-ts)

A UI built with [CRA](https://reactjs.org/docs/create-a-new-react-app.html)

_Start the React dev server_

```
cd ./web-react-ts && npm start
```

## Deployment

### Netlify

This monorepo can be deployed to Netlify. The frontend application will be served over Netlify's CDN and the GraphQL API will be provisioned as a serverless GraphQL API lambda function deployed to AWS (via Netlify). A netlify.toml file is included with the necessary build configurations. The following environment variables must be set in Netlify (either via the Netlify web UI or via the command line tool)

```
NEO4J_URI
NEO4J_USER
NEO4J_PASSWORD
```

See the "Hands On With The GRANDStack Starter" video linked at the beginning of this README for a walkthrough of deploying to Netlify.

### Vercel

Vercel can be used with monorepos such as grand-stack-starter. [`vercel.json`](https://github.com/grand-stack/grand-stack-starter/blob/master/vercel.json) defines the configuration for deploying with Vercel.

1. get [vercel cli](https://vercel.com/download)
2. Set the vercel secrets for your Neo4j instance:

```
vercel secret add grand_stack_starter_neo4j_uri bolt://<YOUR_NEO4J_INSTANCE_HERE>
vercel secret add grand_stack_starter_neo4j_user <YOUR_DATABASE_USERNAME_HERE>
vercel secret add grand_stack_starter_neo4j_password <YOUR_DATABASE_USER_PASSWORD_HERE>
```

3. Run `vercel`

## Docker Compose

You can quickly start via:

```
docker-compose up -d
```

If you want to load the example DB after the services have been started:

```
docker-compose run api npm run seedDb
```

See [the project releases](https://github.com/grand-stack/grand-stack-starter/releases) for the changelog.

You can find instructions for other ways to use Neo4j (Neo4j Desktop, Neo4j Aura, and other cloud services) in the [Neo4j directory README.](./neo4j)

This project is licensed under the Apache License v2.
Copyright (c) 2020 Neo4j, Inc.
