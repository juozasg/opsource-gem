## opsource-gem

Opsource Cloud API gem designed for easy extensibility.

See `lib/opsource/api` folder for examples how to add additional endpoints.

Inspired by https://github.com/udayakiran/opsource.


### Install

either install as a gem via Bundler

__or__

clone into your project, install gems from `opsource.gemspec` and do:

```
$: << 'opsource/lib'
require 'opsource.rb'
```

### Usage

```
api_base      = "https://cloudapi.nttamerica.com/oec/0.9"
dev_org_id    = 'my-super-secret-org-numbersandletters'
dev_user      = 'me'
dev_password  = 'very secret'

c = Opsource::Client.new(api_base, dev_org_id, dev_user, dev_password)

server = c.server.list(name: 'myfavoritevm')
pp c.server.show_with_disks(server.network_id, server.id)
```

### Examples

```
#create a new network
c.network.create("network-name", "description", "EU1")
#list networks
pp c.network.list

```

### Add your own API calls

For already supported methods see:
```
api/directory.rb
api/image.rb
api/network.rb
api/server.rb
api/vip.rb
```

See `doc` folder for API info needed for adding you own methods. `api/core.rb` is the plumbing.


### TODO

Write some tests. Make pull requests.
