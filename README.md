# node_exporter

Prometheus exporter with plugable metric collectors.



## Available collectors

By default it will only include the NativeCollector.

To include other collectors, specify the build tags lile this:

    go build -tags 'ganglia runit' node_exporter.go


### NativeCollector

Provides metrics for load, seconds since last login and a list of tags
read from `node_exporter.conf`.

To disable the native collector, use build tag `nonative`.


### GmondCollector (tag: ganglia)

Talks to a local gmond and provide it's metrics.


### RunitCollector (tag: runit)

Provides metrics for each runit services like state and how long it
has been in that state.
