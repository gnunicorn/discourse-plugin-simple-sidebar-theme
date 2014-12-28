# Discourse Simple-Sidebar-Theme-Plugin

A theme adding a global sidebar to the right onto discourse. Requires the [sidebar plugin](https://github.com/ligthyear/discourse-plugin-sidebar) to be installed.

**Attention**: not having the sidebar plugin installed will break your discourse frontend!


## Installation

### Docker

To install in docker, add the following to your app.yml in the plugins section:

```
hooks:
  after_code:
    - exec:
        cd: $home/plugins
        cmd:
          - mkdir -p plugins
          - git clone https://github.com/discourse/docker_manager.git
          - git clone https://github.com/ligthyear/discourse-plugin-sidebar.git sidebar
          - git clone https://github.com/ligthyear/discourse-plugin-simple-sidebar-theme.git simple-sidebar-theme
```

and rebuild docker via

```
cd /var/discourse
./launcher rebuild app
```

## Manually

Just three simple steps. From your main discourse do:

    cd plugins
    git clone https://github.com/ligthyear/discourse-plugin-simple-sidebar-theme.git simple-sidebar-theme   # clone the repo here
    cd ..
    RAILS_ENV=production rake assets:precompile


## Changelog:

 * 2014-04-28:
   - initial version

## TODO

(in order of importance)

### other Limitations:

 (none)

Found a bug? Please report it on github!

## Authors:
Benjamin Kampmann <ben @ create-build-execute . com>

## License (BSD):
Copyright (c) 2014, Benjamin Kampmann
All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
