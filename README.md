# execute-pr-code-bot

> A GitHub App built with [Probot](https://github.com/probot/probot) that A Probot app to execute the code using the Judge0 API from the pull request whenever a new PR is created.

## Step
Create a Pull Request with the commit message as `/execute` and write your code in the description the PR.
The computed output of the code will be commented automatically by the bot as a comment of the Pull Request.

## Output
![pr-bot-output](./assets/demo.png)

Demo video: [shoot here🚀](https://drive.google.com/file/d/1A4JWbMMGdXjtHFRT95-DUr1zlXG6x0aP/view?usp=sharing)

## Technologies used
    1. Probot - Node.js (Used to create the Github App Bot)
    2. Judge0API - Used to compile the code

## Important Github Events & WebHooks
```sh
    # Events used
    1. pull_request.opened 

    # Webhooks used
    2. context.payload.pull_request
    3. context.octokit.issues.createComment(
        context.issue({
          body: `Output: ${ans}`,
        })

```

## Setup

```sh
# Install dependencies
npm install

# Run the bot
npm start
```

## Docker

```sh
# 1. Build container
docker build -t execute-pr-code-bot .

# 2. Start container
docker run -e APP_ID=<app-id> -e PRIVATE_KEY=<pem-value> execute-pr-code-bot
```


## License

[ISC](LICENSE) © 2023 Shashank-Jha
