# Best Practices
## Resources
* [Julian Dunn's Beginning Chef Antipatterns](http://www.opscode.com/blog/chefconf-talks/beginning-chef-antipatterns-julian-dunn/)
* [Bryan Berry's How To Write Reusable Chef Cookbooks](http://devopsanywhere.blogspot.com/2012/11/how-to-write-reusable-chef-cookbooks.html)
* [Doug Iteron's](http://dougireton.com/blog/2013/02/16/chef-cookbook-anti-patterns/)

## Antipatterns/Patterns
The following list is compiled from the presentations/blog posts below:

1. Create an coobook organization for your cookbooks. Don't just have a `acme/chef-repo` repository with a million cookbooks.
2. Don't create overly large cookbooks. Abstract the cookbook into separate reusable cookbooks/recipes.
3. Use environments only when it maps to how your organizations environments really work.
4. Only fork cookbooks when you intend to create pull requests. Create ORG wrapper cookbooks instead.
5. Run lists shouldn't be put in roles, mainly because they aren't versioned. Create a ORG-roles wrapper
cookbook, so that you can version "role recipes".
6. Organize your databags. Large databags can be detrimental to performance.
7. Use `chef-shell` to test cookbooks.
8. Utilize LWRPs, definitions, and helper methods.
9. "Not Invented Here Syndrome"
10. "Don't be the only Chef in your shop" Make sure other developers in your organization collaborate with you.

## Personal Preferences
1. Use Berkshelf for managing dependencies.
2. Use vagrant to test cookbooks/recipes locally with Chef Solo.
3. Don't overload your attributes file. Create attributes files to map to any recipes that use their own attributes.
Check the run list with: `node.run_list.include? 'cookbook::recipe'` to prevent overriding attributes.
