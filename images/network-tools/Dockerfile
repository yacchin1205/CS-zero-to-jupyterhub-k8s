FROM alpine:3

# VULN_SCAN_TIME=2023-06-19_05:12:47

#RUN apk add --no-cache iptables

# Use iptables-legacy as workaround.
# cf. https://github.com/tailscale/tailscale/issues/10540
RUN apk add --no-cache ca-certificates iptables iptables-legacy
RUN rm /sbin/iptables && ln -s /sbin/iptables-legacy /sbin/iptables
RUN rm /sbin/ip6tables && ln -s /sbin/ip6tables-legacy /sbin/ip6tables
