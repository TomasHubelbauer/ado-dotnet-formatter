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

## Formatters

- https://github.com/dotnet/codeformatter: look to be abandonware
- http://www.narrange.net/: the website doesn't load
- https://github.com/codecadwallader/codemaid: doesn't seem to have a CLI
- https://github.com/DotNetAnalyzers/StyleCopAnalyzers: looks to be supported
- https://github.com/dotnet/format: looks to be supported and easy to use too

I'm going to go with `dotnet-format` for now. It's CLI usage is documented here:
https://github.com/dotnet/format/tree/main/docs

## Experiment

```
dotnet new console
dotnet tool install -g dotnet-format
dotnet format
```

- [ ] Determine only the files changed in the pull request
- [ ] Run the `dotnet-format` tool only for the files changed in the PR
- [ ] Commit and push the changes back from the pipeline to the PR branch
- [ ] See if for multi-project, we need to find changed projects and limit their
  changed files in multiple invocations of the tool (once per each project)
