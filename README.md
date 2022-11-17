# flux-ilias-ilias-base

ILIAS base ilias docker image

First look at [flux-ilias](https://github.com/fluxfw/flux-ilias)

The follow environment variables are available

| Variable | Description | Default value |
| -------- | ----------- | ------------- |
| ILIAS_FILESYSTEM_DATA_DIR | Path to data directory<br>This is a volume | /var/iliasdata |
| ILIAS_FILESYSTEM_INI_PHP_FILE | Path to ILIAS ini file | *%ILIAS_FILESYSTEM_DATA_DIR%*/ilias.ini.php |
| ILIAS_LOG_DIR | Path to ILIAS log directory<br>This is a volume | /var/log/ilias |
| ILIAS_WEB_DIR | Path to ILIAS source code | /var/www/html |
| ILIAS_WEB_DIR_COMPOSER_AUTO_INSTALL | Auto install Ilias core composer dependencies<br>Only use if ILIAS source code is on a volume and composer is not used on host | false |
| ILIAS_CONFIG_FILE | Path to setup config file | *%ILIAS_FILESYSTEM_DATA_DIR%*/config.json |
| ILIAS_FILESYSTEM_WEB_DATA_DIR | Path to web data directory | *%ILIAS_FILESYSTEM_DATA_DIR%*/web |
| ILIAS_PHP_DISPLAY_ERRORS | Directly display PHP errors | Off |
| ILIAS_PHP_ERROR_REPORTING | Error reporting types | E_ALL & ~E_NOTICE & ~E_WARNING & ~E_STRICT |
| ILIAS_PHP_EXPOSE | Expose PHP version | Off |
| ILIAS_PHP_LISTEN | Listen IP | 0.0.0.0 |
| ILIAS_PHP_LOG_ERRORS | Log errors | On |
| ILIAS_PHP_MAX_EXECUTION_TIME | Maximal execution time | 900 |
| ILIAS_PHP_MAX_INPUT_TIME | Maximal input time | 900 |
| ILIAS_PHP_MAX_INPUT_VARS | Maximal input variables | 1000 |
| ILIAS_PHP_MEMORY_LIMIT | Memory limit<br>Should be at least `300M` so composer installation works | 300M |
| ILIAS_PHP_PORT | Listen port | 9000 |
| ILIAS_PHP_POST_MAX_SIZE | Maximal post size | 200M |
| ILIAS_PHP_UPLOAD_MAX_SIZE | Maximal upload size | 200M |
| ILIAS_COMMON_CLIENT_ID | Client name | default |
| ILIAS_COMMON_SERVER_TIMEZONE | Timezone | UTC |
| ILIAS_COMMON_REGISTER_NIC | Register on nic | false |
| ILIAS_BACKGROUNDTASKS_TYPE | Background tasks type | sync |
| ILIAS_BACKGROUNDTASKS_MAX_NUMBER_OF_CONCURRENT_TASKS | Number of concurrent background tasks<br>For async type | 1 |
| ILIAS_DATABASE_TYPE | Database type | innodb |
| ILIAS_DATABASE_HOST | Database host | database |
| ILIAS_DATABASE_PORT | Database port | 3306 |
| ILIAS_DATABASE_DATABASE | Database name | ilias |
| ILIAS_DATABASE_USER | Database user | ilias |
| **ILIAS_DATABASE_PASSWORD** | Database password<br>Use *ILIAS_DATABASE_PASSWORD_FILE* for docker secrets | *-* |
| ILIAS_DATABASE_CREATE_DATABASE | Auto create database | true |
| ILIAS_DATABASE_COLLATION | Init database collation | utf8_general_ci |
| ILIAS_DATABASE_PATH_TO_DB_DUMP | Init database dump (May slow and needs mutch memory, please prefer directly import on database server) | *%ILIAS_WEB_DIR%*/setup/sql/ilias3.sql |
| ILIAS_GLOBALCACHE_SERVICE | Global cache type | *-* |
| ILIAS_GLOBALCACHE_COMPONENTS | Global cache components<br>`all` or separate by spaces | *-* |
| ILIAS_GLOBALCACHE_MEMCACHED_NODES | Memcache nodes<br>JSON string | *-* |
| **ILIAS_HTTP_PATH** | Url the installation can be access<br>Needed for instance on cron context | Try to auto detect, but should be set |
| ILIAS_HTTP_HTTPS_AUTODETECTION_HEADER_NAME | HTTP header name for detect HTTPS if the installation is behind a reserve proxy | *-* |
| ILIAS_HTTP_HTTPS_AUTODETECTION_HEADER_VALUE | HTTP header value for detect HTTPS if the installation is behind a reserve proxy | *-* |
| ILIAS_HTTP_PROXY_HOST | HTTP proxy host for access internet | *-* |
| ILIAS_HTTP_PROXY_PORT | HTTP proxy port for access internet | *-* |
| ILIAS_LANGUAGE_DEFAULT_LANGUAGE | Default language | en |
| ILIAS_LANGUAGE_INSTALL_LANGUAGES | Install languages<br>Separate by spaces | en |
| ILIAS_LANGUAGE_INSTALL_LOCAL_LANGUAGES | Install local languages (From `Customizing` folder)<br>Separate by spaces | *-* |
| ILIAS_LOGGING_ENABLE | Enable log | true |
| ILIAS_LOGGING_PATH_TO_LOGFILE | Path to log file | *%ILIAS_LOG_DIR%*/ilias.log |
| ILIAS_LOGGING_ERRORLOG_DIR | Path to error log directory | *%ILIAS_LOG_DIR%*/errors |
| ILIAS_MATHJAX_CLIENT_ENABLED | Enable client rendering (Only ILIAS 8 or newer) | false |
| ILIAS_MATHJAX_CLIENT_POLYFILL_URL | Legacy browser support script url (Only ILIAS 8 or newer) | *-* |
| ILIAS_MATHJAX_CLIENT_SCRIPT_URL | MathJax main script url (Only ILIAS 8 or newer) | *-* |
| ILIAS_MATHJAX_CLIENT_LIMITER | Type of delimiters (Only ILIAS 8 or newer) | 0 |
| ILIAS_MATHJAX_SERVER_ENABLED | Enable server rendering (Only ILIAS 8 or newer) | false |
| ILIAS_MATHJAX_SERVER_ADDRESS | MathJax server url (Only ILIAS 8 or newer) | *-* |
| ILIAS_MATHJAX_SERVER_TIMEOUT | Timeout to wait MathJax server response (Only ILIAS 8 or newer) | 0 |
| ILIAS_MATHJAX_SERVER_FOR_BROWSER | xxx (Only ILIAS 8 or newer) | false |
| ILIAS_MATHJAX_SERVER_FOR_EXPORT | xxx (Only ILIAS 8 or newer) | false |
| ILIAS_MATHJAX_SERVER_FOR_PDF | xxx (Only ILIAS 8 or newer) | false |
| ILIAS_MATHJAX_PATH_TO_LATEX_CGI | Path to mathjax file (Only ILIAS 7) | *-* |
| ILIAS_MEDIAOBJECT_PATH_TO_FFMPEG | Path to ffmpeg file | /usr/bin/ffmpeg |
| ILIAS_PDFGENERATION_PATH_TO_PHANTOM_JS | Path to phantomjs file | *-* |
| ILIAS_PREVIEW_PATH_TO_GHOSTSCRIPT | Path to gs file | /usr/bin/gs |
| ILIAS_STYLE_MANAGE_SYSTEM_STYLES | Enable manage system styles | false |
| ILIAS_STYLE_PATH_TO_LESSC | Path to lessc file | /usr/share/lessphp/plessc |
| ILIAS_SYSTEMFOLDER_CLIENT_NAME | Name | *-* |
| ILIAS_SYSTEMFOLDER_CLIENT_DESCRIPTION | Description | *-* |
| ILIAS_SYSTEMFOLDER_CLIENT_INSTITUTION | Institution | *-* |
| **ILIAS_SYSTEMFOLDER_CONTACT_FIRSTNAME** | First name | *-* |
| **ILIAS_SYSTEMFOLDER_CONTACT_LASTNAME** | Last name | *-* |
| ILIAS_SYSTEMFOLDER_CONTACT_TITLE | Title | *-* |
| ILIAS_SYSTEMFOLDER_CONTACT_POSITION | Position | *-* |
| ILIAS_SYSTEMFOLDER_CONTACT_INSTITUTION | Institution | *-* |
| ILIAS_SYSTEMFOLDER_CONTACT_STREET | Street name | *-* |
| ILIAS_SYSTEMFOLDER_CONTACT_ZIPCODE | Zip code | *-* |
| ILIAS_SYSTEMFOLDER_CONTACT_CITY | City | *-* |
| ILIAS_SYSTEMFOLDER_CONTACT_COUNTRY | Country code | *-* |
| ILIAS_SYSTEMFOLDER_CONTACT_PHONE | Phone number | *-* |
| **ILIAS_SYSTEMFOLDER_CONTACT_EMAIL** | E mail | *-* |
| ILIAS_UTILITIES_PATH_TO_CONVERT | Path to convert file | /usr/bin/convert |
| ILIAS_UTILITIES_PATH_TO_ZIP | Path to zip file | /usr/bin/zip |
| ILIAS_UTILITIES_PATH_TO_UNZIP | Path to unzip file | /usr/bin/unzip |
| ILIAS_VIRUSSCANNER_VIRUSSCANNER | Virus scanner type | none |
| ILIAS_VIRUSSCANNER_PATH_TO_SCAN | Path to scan file | *-* |
| ILIAS_VIRUSSCANNER_PATH_TO_CLEAN | Path to clean file | *-* |
| ILIAS_VIRUSSCANNER_ICAP_HOST | Icap host | *-* |
| ILIAS_VIRUSSCANNER_ICAP_PORT | Icap port | *-* |
| ILIAS_VIRUSSCANNER_ICAP_SERVICE_NAME | Icap service name | *-* |
| ILIAS_VIRUSSCANNER_ICAP_CLIENT_PATH | Icap client path | *-* |
| ILIAS_PRIVACYSECURITY_HTTPS_ENABLED | Enable HTTPS privacy security on login screen | false |
| ILIAS_PRIVACYSECURITY_AUTH_DURATION | Allowed duration of authentication (Only ILIAS 8 or newer) | *-* |
| ILIAS_PRIVACYSECURITY_ACCOUNT_ASSISTANCE_DURATION | Allowed duration of account assistance (Only ILIAS 8 or newer) | *-* |
| ILIAS_WEBSERVICES_SOAP_USER_ADMINISTRATION | Enable soap user administration | false |
| ILIAS_WEBSERVICES_SOAP_WSDL_PATH | Url soap server can be accessed | *%ILIAS_HTTP_PATH%*/webservice/soap/server.php?wsdl |
| ILIAS_WEBSERVICES_SOAP_CONNECT_TIMEOUT | Soap connection timeout | 10 |
| ILIAS_WEBSERVICES_RPC_SERVER_HOST | ilserver host | ilserver |
| ILIAS_WEBSERVICES_RPC_SERVER_PORT | ilserver port | 11111 |
| ILIAS_LUCENE_SEARCH | Enable lucene search and index cron job | false |
| ILIAS_CHATROOM_ADDRESS | Chatroom server listen IP | 0.0.0.0 |
| ILIAS_CHATROOM_PORT | Chatroom server listen port | 8080 |
| ILIAS_CHATROOM_SUB_DIRECTORY | Chatroom server sub directory | *-* |
| ILIAS_CHATROOM_HTTPS_CERT | Path to HTTPS certificate file<br>Set this will enable listen on HTTPS<br>Should be on a volume | *-* |
| ILIAS_CHATROOM_HTTPS_KEY | Path to HTTPS key file<br>Should be on a volume | *-* |
| ILIAS_CHATROOM_HTTPS_DHPARAM | Path to HTTPS pem file<br>Should be on a volume | *-* |
| ILIAS_CHATROOM_LOG | Path to log file | /dev/stdout |
| ILIAS_CHATROOM_LOG_LEVEL | Log level | info |
| ILIAS_CHATROOM_ERROR_LOG | Path to error log file | /dev/stderr |
| ILIAS_CHATROOM_ILIAS_PROXY_ILIAS_URL | Url ILIAS can access chatroom server | http*s*://chatroom:*%ILIAS_CHATROOM_PORT%* |
| ILIAS_CHATROOM_CLIENT_PROXY_CLIENT_URL | Url client browser can access chatroom server | *%ILIAS_HTTP_PATH%*:*%ILIAS_CHATROOM_PORT%* |
| ILIAS_CHATROOM_DELETION_INTERVAL_DELETION_UNIT | Deletion interval unit | *-* |
| ILIAS_CHATROOM_DELETION_INTERVAL_DELETION_VALUE | Deletion interval value | *-* |
| ILIAS_CHATROOM_DELETION_INTERVAL_DELETION_TIME | Deletion interval time | *-* |
| ILIAS_ROOT_USER_LOGIN | Root user login | root |
| **ILIAS_ROOT_USER_PASSWORD** | Root user password<br>Use *ILIAS_ROOT_USER_PASSWORD_FILE* for docker secrets | *-* |
| ILIAS_CRON_USER_LOGIN | Cron user login<br>This user will be auto created (If the password is set) | cron |
| ILIAS_CRON_USER_PASSWORD | Cron user password<br>Use *ILIAS_CRON_USER_PASSWORD_FILE* for docker secrets | *-* |
| ILIAS_DEVMODE | ILIAS development mode | false |
| ILIAS_SMTP_HOST | SMTP host | *-* |
| ILIAS_SMTP_PORT | SMTP port | *-* |
| ILIAS_SMTP_ENCRYPTION | SMTP encryption | *-* |
| ILIAS_SMTP_USER | SMTP user<br>Use *ILIAS_SMTP_USER_FILE* for docker secrets | *-* |
| ILIAS_SMTP_PASSWORD | SMTP password<br>Use *ILIAS_SMTP_PASSWORD_FILE* for docker secrets | *-* |

Minimal variables required to set are **bold**
