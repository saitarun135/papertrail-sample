1. need to install following package 
`composer require monolog/monolog`

2.Add Destinal details without protocol and port must be a number

3.uncomment the following line in `php.ini` 

`extension=sockets`


4.Finally change like this `config/logging.php`
`
'papertrail' => [
            'driver' => 'monolog',
            'level' => env('LOG_LEVEL', 'debug'),
            'handler' => SyslogUdpHandler::class,
            'handler_with' => [
                'host' => 'lgs6.papertrailapp.com', //don't use protocol either https,tcp,udp...
                'port' => 35377, //it should be a number not a string
            ],
        ],
`
