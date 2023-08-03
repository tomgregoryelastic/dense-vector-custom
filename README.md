## Dense vector custom track

This track is for benchmarking indexing and search on dense vector fields.

`track.json` is the main entry-point.  Inside the `corpora` object, `source-file` specifies where the file containing the vectors is - these vectors will be the data that is ingested into Elasticsearch during the various tests. `track.json` also includes operations and challeneges.  Operations define the individual actions that are going to be undertaken and the challenges file contains the sequence they are to happen in.  

The dataset this rally track was tested on contains 10 million vectors with 96 dimensions.  It is based on the Yandex DEEP1B image dataset, which can be downloaded here:https://big-ann-benchmarks.com/.   

The `queries.json` file contains a list of queries to be used when conducting the testing.  These should be replaced with queries that suit your use-case / data.  

Sample run commands - 

```esrally race --target-hosts=<elastic ip and port> --track-path=<path to the track on your system> --pipeline=benchmark-only --client-options="use_ssl:true,verify_certs:true,basic_auth_user:'<elastic user name>',basic_auth_password:'<password>’” --challenege=<the challenege to run>```


### Parameters

This track accepts the following parameters with Rally 0.8.0+ using `--track-params`:

* `bulk_size` (default: 5000)
* `bulk_indexing_clients` (default: 1): Number of clients that issue bulk indexing requests.
* `index_settings`: A list of index settings. Index settings defined elsewhere (e.g. `number_of_replicas`) need to be overridden explicitly.
* `number_of_replicas` (default: 0)
# dense-vector-custom
# dense-vector-custom
# dense-vector-custom
# dense-vector-custom
# dense-vector-custom
