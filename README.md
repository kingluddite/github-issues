
# How do I migrate issues from one repo to another?
1. You need to have permissions on the repos in question: (the repo you are exporting the issues from and the repo you are importing into).

## Here is a tool that makes working with the GH api effortless
* [github-csv-tools](https://github.com/gavinr/github-csv-tools)

### Here were the steps:
* For all actions, the tool will ask you to input a GitHub token. To obtain this token:

1. Go to https://github.com/settings/tokens
2. Click "Generate New Token"
3. Check the checkbox beside `repo`
4. Copy/paste the token provided when the tool asks for it. (make sure to save it somewhere safe because once you refresh GitHub token page the token won't be able to be seen)

### Now we're ready to migrate:
1. Generate a token from the repo you are exporting from
2. Generate a token from the repo you are importing into
3. Create a file in the root called test.csv and use the following command to export the issues (it will ask you for the token you copied, enter it, your GH username and your repo name)

`$ npx githubCsvTools -f test.csv`

4. Now you have a test.csv file with all your issues
5. Now we import issues into new repo with `$ npx githubCsvTools test.csv` it will ask you for the token you copied, enter it, your GH username and your repo name)
6. At this point you will have successfully moved your issues from GH repo A to GH repo B
