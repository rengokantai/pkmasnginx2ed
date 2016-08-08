#### pkmasnginx2ed
#####
######
test configuration file:
```
nginx -t -c nginx.conf
```
######The HTTP server section
client directives
```
chuck_transfer_encoding
client_body_buffer_size
client_header_buffer_size
client_body_in_file_only
client_body_in_single_buffer
client_body_temp_path
client_body_timeout
client_header_timeout
client_max_body_size   //only body has max_*_size

large_client_header_buffers //only header has large_client

keepalive_requests
keepalive_disable
keepalive_timeout

msie_padding
msie_refresh
```

file_io directives
```
aio
directio
directio_alignment
open_file_cache
open_file_cache_errors
open_file_cache_min_uses
open_file_cache_valid
postpone_output
read_ahead
sendfile
sendfile_max_chunk
```
hash
```
server_names_hash_max_size
server_names_hash_bucket_size
types_hash_max_size
types_hash_bucket_size
variables_hash_max_size
variables_hash_bucket_size
```
