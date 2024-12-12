# label-template
Repository set up with labels

Default labels set for the organisation in Settings > (Code, planning and automation) General are only applied to new repositories.

Following the [blog](https://napjose.ph/posts/copy-issue-labels-from-another-github-repository) to copy labels across repositories using the [GitHub CLI](https://cli.github.com/)
this is a new repository to help try this out.

On terminal:

Log in first

```
gh auth login
```

Suggest set up a specific PAT with required scopes `repo`, `read:org` and `workflow` that is different to the PAT possibly used to connect to R projects.

To check labels in repo:

```
gh label list --repo  nhs-r-community/label-template
```

Clone labels to repo (changing organisation_name/repository to desired place):

```
gh label clone nhs-r-community/label-template --repo organisation_name/repository --force
```

Remove existing but unused labels (note that wherever they have been used already the issue or PR will have a note that they have been removed):

```
gh label delete name-of-label --repo organisation/repo
```
Then you will have to repeat the name of the label again to delete it.

Because some may have been amended to be more explicit like `duplicate` becoming `status:duplicate` the edit command is:

```
gh label edit enhancement --name type:enhancement --description "Propose enhancement" --repo organisation/repo
```
## Quicker code

Instead of using `--repo` the following `-R` can be used. 
