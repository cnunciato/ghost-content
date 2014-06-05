# ghost-content

A collection of public/free themes intended to accompany my [ghost-cookbook for Chef](https://github.com/cnunciato/ghost-cookbook).  

### Usage

First, install [ghost-cookbook for Chef](https://github.com/cnunciato/ghost-cookbook) on your Chef server.  Then include a reference to this repository in either a role definition:

    {
      "name": "ghost-blog",
      "chef_type": "role",
      "json_class": "Chef::Role",
      "override_attributes": {
        "ghost": {
          "remote": {
            "name": "ghost-content",
            "repo": "https://github.com/cnunciato/ghost-content.git",
            "revision": "master"
          }
        }
      },
      "run_list": [
        "recipe[ghost]",
        "recipe[ghost::nginx]"
      ]
    }

... or as a set of ``node`` attributes:

    node.override['ghost']['remote']['name'] = 'ghost-content'
    node.override['ghost']['remote']['repo'] = 'https://github.com/cnunciato/ghost-content.git'
    node.override['ghost']['remote']['revision'] = 'master'

... and the [ghost cookbook](https://github.com/cnunciato/ghost-cookbook) will pick it up automatically.

### About Ghost

Ghost is a free, open, simple blogging platform that's available to anyone who wants to use it. Visit the project's website at <http://ghost.org> for more information.
