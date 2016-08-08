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
socket directives
```
send_timeout
tcp_nopush
tcp_nodelay
```

######Locations – where, when, and how
Locations may be nested except:  
When the prefix is = Or When the location is a named location

#####Chapter 4. NGINX as a Reverse Proxy
######Using error documents to handle


#####Chapter 6. The NGINX HTTP Server
######NGINX's architecture
master process: reading the configuration, handling sockets, spawning workers, opening log files, compiling embedded Perl scripts, responds to administrative requests via signals.  
worker process runs in a tight event loop to handle incoming connections.
######The HTTP core module

######The server directive
```
port_in_redirect
server_name_in_direct
server_tokens
```
log format  (need to memorize)
```
log_format combined '$remote_addr - $remote_user [$time_local] '
'"$request" $status $body_bytes_sent '
'"$http_referer" "$http_user_agent"';
```
autoindex: show directory structure

######Name resolution
valid:ttl
```
server {

  resolver 192.168.100.2 valid=300s;

}
```
```
server {

  resolver 192.168.100.2;

  resolver_timeout 3s;
```
(resolver_timeout is only available with a commercial subscription)

######Restricting access

######Streaming media files
enable:
```
--with-http_flv_module
--with-http_mp4_module
```
directives
```
flv
mp4
mp4_buffer_size
mp4_max_buffer_size
######SPDY and HTTP/2
```
http2_chunk_size
http2_idle_timeout
http2_max_concurrent_streams
http2_max_field_size
http2_max_header_size
http2_recv_buffer_size
http2_recv_timeout
```


#####Chapter 7. NGINX for the Application Developer
######Using the addition module
must enable it at configure time by adding
```
--with-http_addition_module
```
some modules
add_bofore_body
add_after_body
addition_types
```
######The sub module
enable
```
 --with-http_sub_module
 ```
 substitute header:
 ```
 location / {

  sub_filter </head> '<meta name="frontend" content="web3"></head>';

}
```
subsitute multiple times
```
location / {

  sub_filter_once off;

  sub_filter '<img src="img/' '<img src="/img/';

}
```
type filter, only substituye specific type (sub_filter_types)
```
location / {

  sub_filter_types text/css;

  sub_filter url(ke/ 'url(/ke/';

}
```
######The xslt module
