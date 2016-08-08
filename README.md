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
