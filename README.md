# Get started

cd cookbooks
git clone https://github.com/chef-cookbooks/chef-client.git
berks install
berks upload
knife cookbook list

## Terminology

Chef Cookbooks – Cookbooks are how Chef Code is organized. A cookbook contains many files, but the most important of them are recipes, which define what configurations we wish to apply to the systems we manage.

Chef Supermarket – The Chef Supermarket is a publicly available repository of user-created cookbooks that are ready to use. Some are authored by Chef Software and its various partners, and some are written by the Chef community at large. In either case, cookbooks on the Supermarket are open source, and can be inspected or modified to suit an individual or organizations specific needs.

Chef Server – A Chef Server is where cookbooks are stored and provides information about each system you manage. Each managed node has a run list, which defines which recipes need to be run on that particular system. It also maintains a search index of information about our environment so that we can easily identify and manage discrete subsets as needed.

Chef Client – The Chef Client is an agent that runs on each managed system. It communicates with the chef server to pull down any cookbooks required by its run list, executes the recipes therein locally, and reports its results back to the Chef Server when complete.

ChefDK – The Chef Development Kit contains everything we’ll need to get started writing and working with chef cookbooks, including a commandline utility for communicating with the chef server, and testing tools so that we can validate cookbooks locally before updating our environments.