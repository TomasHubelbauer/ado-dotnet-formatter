# Azure DevOps .NET Formatter

Experimenting with developing an Azure DevOps Pipelines step for automatically
formatting changed files in a PR, comitting and pushing the changes back to the
PR branch if any changes had been made.

1. Create a repository https://dev.azure.com/tomashubelbauer/_git/dotnet-formatter
2. Click **Set up build**
3. Click **Starter pipeline**
4. Leave unchanged for now and click **Save and run**
5. Leave the commit message unchanged and click **Save and run**
6. Check https://dev.azure.com/tomashubelbauer/dotnet-formatter/_build
7. Ensure the script outputs were printed as expected

That's the repository and pipeline set up, next up, let's clone the repository
locally, set up a .NET project in it and test out this tool in the pipeline
which looks like it could be able to do the job:

https://github.com/dotnet/codeformatter

- [ ] Set up a .NET project
- [ ] Try out the `codeformatter` tool
- [ ] Find a way to pull the tool in the pipeline
- [ ] Set the pipeline to run the tool
- [ ] Limit the tool to run only on changed files using `/file`
