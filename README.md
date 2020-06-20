# FreeRADIUS Prometheus Exporter

Prometheus exporter for [FreeRADIUS](https://freeradius.org) metrics.

Supports FreeRADIUS 3.0.x.

## Installation

    go get -u github.com/bvantagelimited/freeradius_exporter

## Usage

Name               | Description
-------------------|------------
radius.addr        | Address of [FreeRADIUS status server](https://wiki.freeradius.org/config/Status), defaults to `127.0.0.1:18121`.
radius.secret      | FreeRADIUS client secret.
radius.timeout     | Timeout, in milliseconds, defaults to `5000`.
web.listen-address | Address to listen on for web interface and telemetry, defaults to `:9812`.
web.telemetry-path | Path under which to expose metrics, defaults to `/metrics`.
version            | Display version information

## Environment Variables

Name               | Description
-------------------|------------
RADIUS_ADDR        | Address of [FreeRADIUS status server](https://wiki.freeradius.org/config/Status).
RADIUS_SECRET      | FreeRADIUS client secret.
RADIUS_HOMESERVERS | Addresses of home servers separated by comma, e.g. "172.28.1.2:1812,172.28.1.3:1812"

## Examplary Output

```text
# HELP freeradius_hup_time Epoch timestamp when the server hang up (If start == hup, it hasn't been hup'd yet)
# TYPE freeradius_hup_time gauge
freeradius_hup_time{ip="127.0.0.1",port="18121"} 1.592303548e+09
freeradius_hup_time{ip="172.28.1.2",port="1812"} 1.592303548e+09
freeradius_hup_time{ip="172.28.1.3",port="1812"} 1.592303548e+09
# HELP freeradius_last_packet_recv Epoch timestamp when the last packet was received
# TYPE freeradius_last_packet_recv gauge
freeradius_last_packet_recv{ip="127.0.0.1",port="18121"} -6.21355968e+10
freeradius_last_packet_recv{ip="172.28.1.2",port="1812"} 0
freeradius_last_packet_recv{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_last_packet_sent Epoch timestamp when the last packet was sent
# TYPE freeradius_last_packet_sent gauge
freeradius_last_packet_sent{ip="127.0.0.1",port="18121"} -6.21355968e+10
freeradius_last_packet_sent{ip="172.28.1.2",port="1812"} 0
freeradius_last_packet_sent{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_outstanding_requests Outstanding requests
# TYPE freeradius_outstanding_requests gauge
freeradius_outstanding_requests{ip="127.0.0.1",port="18121"} 0
freeradius_outstanding_requests{ip="172.28.1.2",port="1812"} 0
freeradius_outstanding_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_queue_len_acct Acct queue length
# TYPE freeradius_queue_len_acct gauge
freeradius_queue_len_acct{ip="127.0.0.1",port="18121"} 0
freeradius_queue_len_acct{ip="172.28.1.2",port="1812"} 0
freeradius_queue_len_acct{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_queue_len_auth Auth queue length
# TYPE freeradius_queue_len_auth gauge
freeradius_queue_len_auth{ip="127.0.0.1",port="18121"} 0
freeradius_queue_len_auth{ip="172.28.1.2",port="1812"} 0
freeradius_queue_len_auth{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_queue_len_detail Detail queue length
# TYPE freeradius_queue_len_detail gauge
freeradius_queue_len_detail{ip="127.0.0.1",port="18121"} 0
freeradius_queue_len_detail{ip="172.28.1.2",port="1812"} 0
freeradius_queue_len_detail{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_queue_len_internal Interal queue length
# TYPE freeradius_queue_len_internal gauge
freeradius_queue_len_internal{ip="127.0.0.1",port="18121"} 0
freeradius_queue_len_internal{ip="172.28.1.2",port="1812"} 0
freeradius_queue_len_internal{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_queue_len_proxy Proxy queue length
# TYPE freeradius_queue_len_proxy gauge
freeradius_queue_len_proxy{ip="127.0.0.1",port="18121"} 0
freeradius_queue_len_proxy{ip="172.28.1.2",port="1812"} 0
freeradius_queue_len_proxy{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_queue_pps_in Queue PPS in
# TYPE freeradius_queue_pps_in gauge
freeradius_queue_pps_in{ip="127.0.0.1",port="18121"} 0
freeradius_queue_pps_in{ip="172.28.1.2",port="1812"} 0
freeradius_queue_pps_in{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_queue_pps_out Queue PPS out
# TYPE freeradius_queue_pps_out gauge
freeradius_queue_pps_out{ip="127.0.0.1",port="18121"} 0
freeradius_queue_pps_out{ip="172.28.1.2",port="1812"} 0
freeradius_queue_pps_out{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_queue_use_percentage Queue usage percentage
# TYPE freeradius_queue_use_percentage gauge
freeradius_queue_use_percentage{ip="127.0.0.1",port="18121"} 0
freeradius_queue_use_percentage{ip="172.28.1.2",port="1812"} 0
freeradius_queue_use_percentage{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_start_time Epoch timestamp when the server was started
# TYPE freeradius_start_time gauge
freeradius_start_time{ip="127.0.0.1",port="18121"} 1.592303548e+09
freeradius_start_time{ip="172.28.1.2",port="1812"} 1.592303548e+09
freeradius_start_time{ip="172.28.1.3",port="1812"} 1.592303548e+09
# HELP freeradius_state State of the server. Alive = 0; Zombie = 1; Dead = 2; Idle = 3
# TYPE freeradius_state gauge
freeradius_state{ip="127.0.0.1",port="18121"} 0
freeradius_state{ip="172.28.1.2",port="1812"} 0
freeradius_state{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_time_of_death Epoch timestamp when a home server is marked as 'dead'
# TYPE freeradius_time_of_death gauge
freeradius_time_of_death{ip="127.0.0.1",port="18121"} -6.21355968e+10
freeradius_time_of_death{ip="172.28.1.2",port="1812"} -6.21355968e+10
freeradius_time_of_death{ip="172.28.1.3",port="1812"} -6.21355968e+10
# HELP freeradius_time_of_life Epoch timestamp when a home server is marked as 'alive'
# TYPE freeradius_time_of_life gauge
freeradius_time_of_life{ip="127.0.0.1",port="18121"} -6.21355968e+10
freeradius_time_of_life{ip="172.28.1.2",port="1812"} -6.21355968e+10
freeradius_time_of_life{ip="172.28.1.3",port="1812"} -6.21355968e+10
# HELP freeradius_total_access_accepts Total access accepts
# TYPE freeradius_total_access_accepts counter
freeradius_total_access_accepts{ip="127.0.0.1",port="18121"} 0
freeradius_total_access_accepts{ip="172.28.1.2",port="1812"} 0
freeradius_total_access_accepts{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_access_challenges Total access challenges
# TYPE freeradius_total_access_challenges counter
freeradius_total_access_challenges{ip="127.0.0.1",port="18121"} 0
freeradius_total_access_challenges{ip="172.28.1.2",port="1812"} 0
freeradius_total_access_challenges{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_access_rejects Total access rejects
# TYPE freeradius_total_access_rejects counter
freeradius_total_access_rejects{ip="127.0.0.1",port="18121"} 0
freeradius_total_access_rejects{ip="172.28.1.2",port="1812"} 0
freeradius_total_access_rejects{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_access_requests Total access requests
# TYPE freeradius_total_access_requests counter
freeradius_total_access_requests{ip="127.0.0.1",port="18121"} 10
freeradius_total_access_requests{ip="172.28.1.2",port="1812"} 0
freeradius_total_access_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_acct_dropped_requests Total acct dropped requests
# TYPE freeradius_total_acct_dropped_requests counter
freeradius_total_acct_dropped_requests{ip="127.0.0.1",port="18121"} 0
freeradius_total_acct_dropped_requests{ip="172.28.1.2",port="1812"} 0
freeradius_total_acct_dropped_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_acct_duplicate_requests Total acct duplicate requests
# TYPE freeradius_total_acct_duplicate_requests counter
freeradius_total_acct_duplicate_requests{ip="127.0.0.1",port="18121"} 0
freeradius_total_acct_duplicate_requests{ip="172.28.1.2",port="1812"} 0
freeradius_total_acct_duplicate_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_acct_invalid_requests Total acct invalid requests
# TYPE freeradius_total_acct_invalid_requests counter
freeradius_total_acct_invalid_requests{ip="127.0.0.1",port="18121"} 0
freeradius_total_acct_invalid_requests{ip="172.28.1.2",port="1812"} 0
freeradius_total_acct_invalid_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_acct_malformed_requests Total acct malformed requests
# TYPE freeradius_total_acct_malformed_requests counter
freeradius_total_acct_malformed_requests{ip="127.0.0.1",port="18121"} 0
freeradius_total_acct_malformed_requests{ip="172.28.1.2",port="1812"} 0
freeradius_total_acct_malformed_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_acct_requests Total acct requests
# TYPE freeradius_total_acct_requests counter
freeradius_total_acct_requests{ip="127.0.0.1",port="18121"} 0
freeradius_total_acct_requests{ip="172.28.1.2",port="1812"} 0
freeradius_total_acct_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_acct_responses Total acct responses
# TYPE freeradius_total_acct_responses counter
freeradius_total_acct_responses{ip="127.0.0.1",port="18121"} 0
freeradius_total_acct_responses{ip="172.28.1.2",port="1812"} 0
freeradius_total_acct_responses{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_acct_unknown_types Total acct unknown types
# TYPE freeradius_total_acct_unknown_types counter
freeradius_total_acct_unknown_types{ip="127.0.0.1",port="18121"} 0
freeradius_total_acct_unknown_types{ip="172.28.1.2",port="1812"} 0
freeradius_total_acct_unknown_types{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_auth_dropped_requests Total auth dropped requests
# TYPE freeradius_total_auth_dropped_requests counter
freeradius_total_auth_dropped_requests{ip="127.0.0.1",port="18121"} 0
freeradius_total_auth_dropped_requests{ip="172.28.1.2",port="1812"} 0
freeradius_total_auth_dropped_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_auth_duplicate_requests Total auth duplicate requests
# TYPE freeradius_total_auth_duplicate_requests counter
freeradius_total_auth_duplicate_requests{ip="127.0.0.1",port="18121"} 0
freeradius_total_auth_duplicate_requests{ip="172.28.1.2",port="1812"} 0
freeradius_total_auth_duplicate_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_auth_invalid_requests Total auth invalid requests
# TYPE freeradius_total_auth_invalid_requests counter
freeradius_total_auth_invalid_requests{ip="127.0.0.1",port="18121"} 0
freeradius_total_auth_invalid_requests{ip="172.28.1.2",port="1812"} 0
freeradius_total_auth_invalid_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_auth_malformed_requests Total auth malformed requests
# TYPE freeradius_total_auth_malformed_requests counter
freeradius_total_auth_malformed_requests{ip="127.0.0.1",port="18121"} 0
freeradius_total_auth_malformed_requests{ip="172.28.1.2",port="1812"} 0
freeradius_total_auth_malformed_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_auth_responses Total auth responses
# TYPE freeradius_total_auth_responses counter
freeradius_total_auth_responses{ip="127.0.0.1",port="18121"} 0
freeradius_total_auth_responses{ip="172.28.1.2",port="1812"} 0
freeradius_total_auth_responses{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_auth_unknown_types Total auth unknown types
# TYPE freeradius_total_auth_unknown_types counter
freeradius_total_auth_unknown_types{ip="127.0.0.1",port="18121"} 0
freeradius_total_auth_unknown_types{ip="172.28.1.2",port="1812"} 0
freeradius_total_auth_unknown_types{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_proxy_access_accepts Total proxy access accepts
# TYPE freeradius_total_proxy_access_accepts counter
freeradius_total_proxy_access_accepts{ip="127.0.0.1",port="18121"} 0
freeradius_total_proxy_access_accepts{ip="172.28.1.2",port="1812"} 0
freeradius_total_proxy_access_accepts{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_proxy_access_challenges Total proxy access challenges
# TYPE freeradius_total_proxy_access_challenges counter
freeradius_total_proxy_access_challenges{ip="127.0.0.1",port="18121"} 0
freeradius_total_proxy_access_challenges{ip="172.28.1.2",port="1812"} 0
freeradius_total_proxy_access_challenges{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_proxy_access_rejects Total proxy access rejects
# TYPE freeradius_total_proxy_access_rejects counter
freeradius_total_proxy_access_rejects{ip="127.0.0.1",port="18121"} 0
freeradius_total_proxy_access_rejects{ip="172.28.1.2",port="1812"} 0
freeradius_total_proxy_access_rejects{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_proxy_access_requests Total proxy access requests
# TYPE freeradius_total_proxy_access_requests counter
freeradius_total_proxy_access_requests{ip="127.0.0.1",port="18121"} 0
freeradius_total_proxy_access_requests{ip="172.28.1.2",port="1812"} 0
freeradius_total_proxy_access_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_proxy_acct_dropped_requests Total proxy acct dropped requests
# TYPE freeradius_total_proxy_acct_dropped_requests counter
freeradius_total_proxy_acct_dropped_requests{ip="127.0.0.1",port="18121"} 0
freeradius_total_proxy_acct_dropped_requests{ip="172.28.1.2",port="1812"} 0
freeradius_total_proxy_acct_dropped_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_proxy_acct_duplicate_requests Total proxy acct duplicate requests
# TYPE freeradius_total_proxy_acct_duplicate_requests counter
freeradius_total_proxy_acct_duplicate_requests{ip="127.0.0.1",port="18121"} 0
freeradius_total_proxy_acct_duplicate_requests{ip="172.28.1.2",port="1812"} 0
freeradius_total_proxy_acct_duplicate_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_proxy_acct_invalid_requests Total proxy acct invalid requests
# TYPE freeradius_total_proxy_acct_invalid_requests counter
freeradius_total_proxy_acct_invalid_requests{ip="127.0.0.1",port="18121"} 0
freeradius_total_proxy_acct_invalid_requests{ip="172.28.1.2",port="1812"} 0
freeradius_total_proxy_acct_invalid_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_proxy_acct_malformed_requests Total proxy acct malformed requests
# TYPE freeradius_total_proxy_acct_malformed_requests counter
freeradius_total_proxy_acct_malformed_requests{ip="127.0.0.1",port="18121"} 0
freeradius_total_proxy_acct_malformed_requests{ip="172.28.1.2",port="1812"} 0
freeradius_total_proxy_acct_malformed_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_proxy_acct_requests Total proxy acct requests
# TYPE freeradius_total_proxy_acct_requests counter
freeradius_total_proxy_acct_requests{ip="127.0.0.1",port="18121"} 0
freeradius_total_proxy_acct_requests{ip="172.28.1.2",port="1812"} 0
freeradius_total_proxy_acct_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_proxy_acct_responses Total proxy acct responses
# TYPE freeradius_total_proxy_acct_responses counter
freeradius_total_proxy_acct_responses{ip="127.0.0.1",port="18121"} 0
freeradius_total_proxy_acct_responses{ip="172.28.1.2",port="1812"} 0
freeradius_total_proxy_acct_responses{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_proxy_acct_unknown_types Total proxy acct unknown types
# TYPE freeradius_total_proxy_acct_unknown_types counter
freeradius_total_proxy_acct_unknown_types{ip="127.0.0.1",port="18121"} 0
freeradius_total_proxy_acct_unknown_types{ip="172.28.1.2",port="1812"} 0
freeradius_total_proxy_acct_unknown_types{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_proxy_auth_dropped_requests Total proxy auth dropped requests
# TYPE freeradius_total_proxy_auth_dropped_requests counter
freeradius_total_proxy_auth_dropped_requests{ip="127.0.0.1",port="18121"} 0
freeradius_total_proxy_auth_dropped_requests{ip="172.28.1.2",port="1812"} 0
freeradius_total_proxy_auth_dropped_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_proxy_auth_duplicate_requests Total proxy auth duplicate requests
# TYPE freeradius_total_proxy_auth_duplicate_requests counter
freeradius_total_proxy_auth_duplicate_requests{ip="127.0.0.1",port="18121"} 0
freeradius_total_proxy_auth_duplicate_requests{ip="172.28.1.2",port="1812"} 0
freeradius_total_proxy_auth_duplicate_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_proxy_auth_invalid_requests Total proxy auth invalid requests
# TYPE freeradius_total_proxy_auth_invalid_requests counter
freeradius_total_proxy_auth_invalid_requests{ip="127.0.0.1",port="18121"} 0
freeradius_total_proxy_auth_invalid_requests{ip="172.28.1.2",port="1812"} 0
freeradius_total_proxy_auth_invalid_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_proxy_auth_malformed_requests Total proxy auth malformed requests
# TYPE freeradius_total_proxy_auth_malformed_requests counter
freeradius_total_proxy_auth_malformed_requests{ip="127.0.0.1",port="18121"} 0
freeradius_total_proxy_auth_malformed_requests{ip="172.28.1.2",port="1812"} 0
freeradius_total_proxy_auth_malformed_requests{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_proxy_auth_responses Total proxy auth responses
# TYPE freeradius_total_proxy_auth_responses counter
freeradius_total_proxy_auth_responses{ip="127.0.0.1",port="18121"} 0
freeradius_total_proxy_auth_responses{ip="172.28.1.2",port="1812"} 0
freeradius_total_proxy_auth_responses{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_total_proxy_auth_unknown_types Total proxy auth unknown types
# TYPE freeradius_total_proxy_auth_unknown_types counter
freeradius_total_proxy_auth_unknown_types{ip="127.0.0.1",port="18121"} 0
freeradius_total_proxy_auth_unknown_types{ip="172.28.1.2",port="1812"} 0
freeradius_total_proxy_auth_unknown_types{ip="172.28.1.3",port="1812"} 0
# HELP freeradius_up Boolean gauge of 1 if freeradius was reachable, or 0 if not
# TYPE freeradius_up gauge
freeradius_up 1
```

## Dev Environment

Mount with sites-enabled dir from this repository:

    docker-compose up --remove-orphans 

Run the exporter:

    go run main.go

Access the metrics at http://127.0.0.1:9812/metrics

### Dictionaries

- https://fossies.org/linux/freeradius-server/share/dictionary.freeradius
- https://cs.fit.edu/code/projects/cse2410spring2014_team4/repository/revisions/master/entry/radius/dictionary.freeradius
- https://gitlab.com/kalilinux/packages/freeradius-wpe/-/blob/upstream/share/dictionary.freeradius

### sending manual reqeusts to stat server

    brew install freeradius-server

request (wrong auth but will update `freeradius_last_packet_sent` metric):

```bash
echo "User-Name = bob" | /usr/local/bin/radclient localhost:1812 auth test123
```

or

request:

```bash
echo "Message-Authenticator = 0x00,FreeRADIUS-Statistics-Type = 159, FreeRADIUS-Stats-Server-IP-Address = 172.28.1.2, FreeRADIUS-Stats-Server-Port = 1812" | radclient -x localhost:18121 status adminsecret
```

response:

```text
Sent Status-Server Id 188 from 0.0.0.0:54304 to 127.0.0.1:18121 length 74
	Message-Authenticator = 0x00
	FreeRADIUS-Statistics-Type = 159
	FreeRADIUS-Stats-Server-IP-Address = 172.28.1.2
	FreeRADIUS-Stats-Server-Port = 1812
Received Access-Accept Id 188 from 127.0.0.1:18121 to 127.0.0.1:54304 length 567
	FreeRADIUS-Total-Proxy-Access-Requests = 3
	FreeRADIUS-Total-Proxy-Access-Accepts = 0
	FreeRADIUS-Total-Proxy-Access-Rejects = 0
	FreeRADIUS-Total-Proxy-Access-Challenges = 0
	FreeRADIUS-Total-Proxy-Auth-Responses = 0
	FreeRADIUS-Total-Proxy-Auth-Duplicate-Requests = 0
	FreeRADIUS-Total-Proxy-Auth-Malformed-Requests = 0
	FreeRADIUS-Total-Proxy-Auth-Invalid-Requests = 0
	FreeRADIUS-Total-Proxy-Auth-Dropped-Requests = 0
	FreeRADIUS-Total-Proxy-Auth-Unknown-Types = 0
	FreeRADIUS-Total-Proxy-Accounting-Requests = 0
	FreeRADIUS-Total-Proxy-Accounting-Responses = 0
	FreeRADIUS-Total-Proxy-Acct-Duplicate-Requests = 0
	FreeRADIUS-Total-Proxy-Acct-Malformed-Requests = 0
	FreeRADIUS-Total-Proxy-Acct-Invalid-Requests = 0
	FreeRADIUS-Total-Proxy-Acct-Dropped-Requests = 0
	FreeRADIUS-Total-Proxy-Acct-Unknown-Types = 0
	FreeRADIUS-Stats-Start-Time = "Jun 15 2020 16:27:37 CEST"
	FreeRADIUS-Stats-HUP-Time = "Jun 15 2020 16:27:37 CEST"
	FreeRADIUS-Queue-Len-Internal = 0
	FreeRADIUS-Queue-Len-Proxy = 0
	FreeRADIUS-Queue-Len-Auth = 0
	FreeRADIUS-Queue-Len-Acct = 0
	FreeRADIUS-Queue-Len-Detail = 0
	FreeRADIUS-Queue-PPS-In = 0
	FreeRADIUS-Queue-PPS-Out = 0
	FreeRADIUS-Stats-Server-IP-Address = 172.28.1.2
	FreeRADIUS-Stats-Server-Port = 1812
	FreeRADIUS-Stats-Server-Outstanding-Requests = 0
	FreeRADIUS-Stats-Server-State = Idle
	FreeRADIUS-Stats-Server-Time-Of-Death = "Jun 15 2020 16:28:56 CEST"
	FreeRADIUS-Stats-Last-Packet-Recv = "Jan  1 1970 01:00:00 CET"
	FreeRADIUS-Stats-Last-Packet-Sent = "Jun 15 2020 16:28:06 CEST"
	FreeRADIUS-Total-Proxy-Access-Requests = 5
	FreeRADIUS-Total-Proxy-Access-Accepts = 0
	FreeRADIUS-Total-Proxy-Access-Rejects = 0
	FreeRADIUS-Total-Proxy-Access-Challenges = 0
	FreeRADIUS-Total-Proxy-Auth-Responses = 0
	FreeRADIUS-Total-Proxy-Auth-Duplicate-Requests = 0
	FreeRADIUS-Total-Proxy-Auth-Malformed-Requests = 0
	FreeRADIUS-Total-Proxy-Auth-Invalid-Requests = 0
	FreeRADIUS-Total-Proxy-Auth-Dropped-Requests = 0
	FreeRADIUS-Total-Proxy-Auth-Unknown-Types = 0
	FreeRADIUS-Stats-Error = "Home server is not acct"
```
