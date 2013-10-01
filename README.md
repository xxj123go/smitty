# smitty

smitty is an agent for [twemproxy](https://github.com/twitter/twemproxy) configured to work with [redis
sentinel](http://redis.io/topics/sentinel). Its purpose is maintain the twemproxy's configuration
updated with the active redis masters. For this, smitty monitors for
the **+switch-master** event, updates twemproxy configuration and restarts
the twemproxy process.

### A possible scenario:

![Image](stack.png)

## Install

You can get the latest [release](https://github.com/areina/smitty/releases) that includes a smitty binary,
download and run it. 

## Configuration

smitty needs to be configured through a YAML file specified by the -c
command-line argument on process start. An example of configuration
file, also included in [conf/agent.yml](conf/agent.yml) could be this:

    twemproxy_pool_name: "root"
    twemproxy_config_file: "conf/nutcracker.yml"
    sentinel_ip: "127.0.0.1"
    sentinel_port: "26379"
    restart_command: "/etc/init.d/twemproxy restart"
    log_file: "agent.log"

## The name

In [3scale](http://3scale.net), we're an absolute Futurama fanatics,
and of course there isn't a better name for an agent that Smitty:

![Image](smitty.jpg)

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## License

Licensed under the Apache License, Version 2.0: http://www.apache.org/licenses/LICENSE-2.0

See [LICENSE.md](LICENSE)
