# Universal Messaging Realm Server

Use this template to provision and migrate Universal Messaging Realm Server.

## Requirements

### Supported Software AG releases

* Universal Messaging 9.8 and higher
* Command Central 10.2 and higher

### Supported platforms

All supported Windows and UNIX platforms.

### Supported use cases

* Provisioning of new 9.8 or higher environments
* Installing latest fixes and support patches
* In-place upgrades to 9.12 or higher
* Cross-host migrations to 9.12 or higher
* Configuration of:
  * License
  * JVM memory
  * NHP and JMX ports

## Running as a composite template

> NOTE: to provision a new 9.8+ node use any of the `sag-spm-*` templates.

Provisions `default` instance of Universal Messaging Realm 10.1 server with all latest fixes,
listening on default ports
9000 and 9988 (jmx), with 512mb of memory:

```bash
sagcc exec templates composite apply sag-um-server nodes=dev1 \
  um.memory.max=512 \
  repo.product=webMethods-10.1 \
  repo.fix=Empower \
  --sync-job --wait 360
```

## Creating a new stack with Universal Messaging layer using Web UI

* Open Stacks UI
* Add new stack by clicking `(+)` icon
* Add new Infrastructure layer
* Add new Runtime layer
  * Select UM-SERVER layer definition
  * Select product and fix repositories
  * Select exactly one node on which to provision Univesal Messaging Realm server
  * Review and adjust optional parameters as needed
  * Finish the wizard
* Wait until provision jobs completes. Use Jobs view to monitor
