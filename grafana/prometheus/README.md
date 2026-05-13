Please edit those line in prometheus.yml

  - job_name: 'server_group_name' # Name display in nodename section for the group #
    static_configs:
      - targets:
          - 'IP_ADDRESS:9100' # Ip Address of the machine to monitor #
          - 'IP_ADDRESS:9100' # Ip Address of the machine to monitor #
          - 'IP_ADDRESS:9100' # Ip Address of the machine to monitor #
          - 'IP_ADDRESS:9100' # Ip Address of the machine to monitor #
          - 'IP_ADDRESS:9100' # Ip Address of the machine to monitor #

  - job_name: 'server_name' # Name display in nodename section #
    static_configs:
      - targets:
          - 'IP_ADDRESS:9100' # Ip Address of the machine to monitor #
