# FIXME: use of alpine:3.19 makes iptables work in "nf_tables" mode instead of
#        "legacy" mode, and then our init container breaks.
#
#        ref: https://github.com/jupyterhub/zero-to-jupyterhub-k8s/issues/3368
#
FROM alpine:3.18

# VULN_SCAN_TIME=2024-09-16_05:05:41

#RUN apk add --no-cache iptables

# Use iptables-legacy as workaround.
# cf. https://github.com/tailscale/tailscale/issues/10540
RUN apk add --no-cache ca-certificates iptables iptables-legacy
RUN rm /sbin/iptables && ln -s /sbin/iptables-legacy /sbin/iptables
RUN rm /sbin/ip6tables && ln -s /sbin/ip6tables-legacy /sbin/ip6tables
