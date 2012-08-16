Adjust the parameters to your needs (parameters.yml/parameters.ini):

parameters:
    graylog.hostname: graylog.example.com
    graylog.port: 12201

    # DEBUG
    # monolog.handler.gelf.debug_level: 100
    # INFO (default)
    monolog.handler.gelf.debug_level: 200
    # WARNING
    # monolog.handler.gelf.debug_level: 300
    # ERROR
    # monolog.handler.gelf.debug_level: 400
    # CRITICAL
    # monolog.handler.gelf.debug_level: 500
    # ALERT
    # monolog.handler.gelf.debug_level: 550


Add next to config.yml

monolog:
    handlers:
        main:
            type: stream
            handler: gelf
            level: WARNING
        gelf:
            type: service
            id: monolog.gelf_handler
