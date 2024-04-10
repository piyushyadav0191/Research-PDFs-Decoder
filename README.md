# Research-PDFs-Decoder

![Image](https://i.ibb.co/wRSgNNf/Screenshot-2024-04-10-19-33-28-1920x1080.png)

## Introduction
Research Pdf Decoder is a Full Stack side project which focus on extracting important notes from any Research papers PDF. It also capable of chatting with PDFs

## Setup

### Prerequisites
- Docker
- Node.js
- Yarn package manager
- Supabase account
- Unstructured API key

### Environment Configuration
Create a `.env.development.local` file in the `./api` directory with the following content:

```shell
UNSTRUCTURED_API_KEY=<YOUR_API_KEY>
SUPABASE_PRIVATE_KEY=<YOUR_API_KEY>
SUPABASE_URL=<YOUR_URL>
OPENAI_API_KEY=<YOUR_API_KEY>
```

### Starting Unstructured with Docker

Start a local instance of Unstructured with the following Docker command:

```shell
docker run -p 8000:8000 -d --rm --name unstructured-api quay.io/unstructured-io/unstructured-api:latest --port 8000 --host 0.0.0.0
```

### Database Setup in Supabase

You can contact me for database query commands 

### Supabase Type Generation

Add your project ID to the Supabase generate types script in package.json:

```json
{
  "gen:supabase:types": "touch ./src/generated.ts && supabase gen types typescript --schema public > ./src/generated.ts --project-id <YOUR_PROJECT_ID>"
}
```

## Limitations

- As of now, It supports Max page limit of 12 due to tokens.

## Running the Application

### Build the API Server

```shell
yarn build
```

### Start the API Server

```shell
yarn start:api
```

### Start the Web Server

```shell
yarn start:web
```

