# Best Practices
Watch Julian Dunn's presentation on antipatterns here: http://www.opscode.com/blog/chefconf-talks/beginning-chef-antipatterns-julian-dunn/

1. Create an coobook organization for your cookbooks.
2. Don't create overly large cookbooks. Abstract the cookbook into separate top level service cookbooks.
3. Only fork cookbooks when you intend to create pull requests. Create wrapper cookbooks instead.
4. Run lists shouldn't be put in roles, mainly because they aren't versioned. Create a ORG-roles wrapper
cookbook, so that you can version role "recipes" you create.
5. Organize your databags. Large databags can be detrimental to performance.
