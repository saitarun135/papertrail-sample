1. need to install following package 
`composer require monolog/monolog`

2.Add Destinal details without protocol and port must be a number

3.uncomment the following line in `php.ini` 

`extension=sockets`

`config/logging.php`

`
'papertrail' => [
            'driver' => 'monolog',
            'level' => env('LOG_LEVEL', 'debug'),
            'handler' => SyslogUdpHandler::class,
            'handler_with' => [
                'host' => 'lgs6.papertrailapp.com',
                'port' => 35377,
            ],
        ],
`
