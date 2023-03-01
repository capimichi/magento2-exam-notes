# Frontend Commands

## app

### app:config:dump

Create dump of application

Arguments

- config-types: Space-separated list of config types or omit to dump all [scopes, themes, system, i18n]

### app:config:import

Import data from shared configuration files to appropriate data storage

### app:config:status

Checks if config propagation requires update

## cache

### cache:clean

Cleans cache type(s)

Arguments

- types: Space-separated list of cache types or omit to apply to all cache types.

Options

- --bootstrap=BOOTSTRAP  add or override parameters of the bootstrap

### cache:disable

Disables cache type(s)

Arguments

- types: Space-separated list of cache types or omit to apply to all cache types.

Options

- --bootstrap=BOOTSTRAP  add or override parameters of the bootstrap

### cache:enable

Enables cache type(s)

Arguments

- types: Space-separated list of cache types or omit to apply to all cache types.

Options

- --bootstrap=BOOTSTRAP  add or override parameters of the bootstrap

### cache:flush

Flushes cache storage used by cache type(s)

Arguments

- types: Space-separated list of cache types or omit to apply to all cache types.

Options

- --bootstrap=BOOTSTRAP  add or override parameters of the bootstrap

### cache:status

Checks cache status

Options

- --bootstrap=BOOTSTRAP  add or override parameters of the bootstrap

## catalog

### catalog:images:resize

Creates resized product images

Options

- -a, --async Resize image in asynchronous mode
- --skip_hidden_images  Do not process images marked as hidden from product page

### catalog:product:attributes:cleanup

Removes unused product attributes.

## config

### config:sensitive:set

Set sensitive configuration values

Arguments

- path                           Configuration path for example group/section/field_name
- value                          Configuration value

Options

- -i, --interactive              Enable interactive mode to set all sensitive variables
- --scope[=SCOPE]            Scope for configuration, if not set use 'default' [default: "default"]
- --scope-code[=SCOPE-CODE]  Scope code for configuration, empty string by default [default: ""]


### config:set

Change system configuration

Arguments

- path                         Configuration path in format section/group/field_name
- value                        Configuration value

Options

- --scope=SCOPE            Configuration scope (default, website, or store) [default: "default"]
- --scope-code=SCOPE-CODE  Scope code (required only if scope is not 'default')
- -e, --lock-env               Lock value which prevents modification in the Admin (will be saved in app/etc/env.php)
- -c, --lock-config            Lock and share value with other installations, prevents modification in the Admin (will be saved in app/etc/config.php)
- -l, --lock                   Deprecated, use the --lock-env option instead.

### config:show

Shows configuration value for given path. If path is not specified, all saved values will be shown

Arguments

- path                           Configuration path, for example section_id/group_id/field_id

Options

- --scope[=SCOPE]            Scope for configuration, if not specified, then 'default' scope will be used [default: "default"]
- --scope-code[=SCOPE-CODE]  Scope code (required only if scope is not `default`) [default: ""]

## deploy

### deploy:mode:set

Set application mode.

Arguments:

- mode                    The application mode to set. Available options are "developer" or "production"

Options:

- -s, --skip-compilation  Skips the clearing and regeneration of static content (generated code, preprocessed CSS, and assets in pub/static/)

### deploy:mode:show

Displays current application mode.

## dev

### dev:email:newsletter-compatibility-check             

Scans newsletter templates for potential variable usage compatibility issues

### dev:email:override-compatibility-check

Scans email template overrides for potential variable usage compatibility issues

### dev:profiler:disable

Disable the profiler.

### dev:profiler:enable

Enable the profiler.

Arguments:

- type                  Profiler type

### dev:source-theme:deploy

Collects and publishes source files for theme.

Arguments:

- file                  Files to pre-process (file should be specified without extension) [default: ["css/styles-m","css/styles-l"]]

Options:

- --type=TYPE       Type of source files: [less] [default: "less"]
- --locale=LOCALE   Locale: [en_US] [default: "en_US"]
- --area=AREA       Area: [frontend|adminhtml] [default: "frontend"]
- --theme=THEME     Theme: [Vendor/theme] [default: "Magento/luma"]

### dev:template-hints:disable

Disable frontend template hints. A cache flush might be required.

### dev:template-hints:enable

Enable frontend template hints. A cache flush might be required.

### dev:template-hints:status

Show frontend template hints status.

## i18n

### i18n:collect-phrases

Discovers phrases in the codebase

Arguments:

- directory             Directory path to parse. Not needed if --magento flag is set

Options:

- -o, --output=OUTPUT   Path (including filename) to an output file. With no file specified, defaults to stdout.
- -m, --magento         Use the --magento parameter to parse the current Magento codebase. Omit the parameter if a directory is specified.

### i18n:pack

Saves language package

Arguments:

- source                  Path to source dictionary file with translations
- locale                  Target locale for dictionary, for example "de_DE"

Options:

- -m, --mode=MODE         Save mode for dictionary
- - "replace" - replace language pack by new one
- - "merge" - merge language packages, by default "replace" [default: "replace"]
- -d, --allow-duplicates  Use the --allow-duplicates parameter to allow saving duplicates of translate. Otherwise omit the parameter.

### i18n:uninstall

Uninstalls language packages

Arguments:

- package               Language package name

Options:

- -b, --backup-code     Take code and configuration files backup (excluding temporary files)

## maintenance

### maintenance:allow-ips

Sets maintenance mode exempt IPs

Arguments:

- ip                                             Allowed IP addresses

Options:

- --none                                     Clear allowed IP addresses
- --add                                      Add the IP address to existing list
- --magento-init-params=MAGENTO-INIT-PARAMS  Add to any command to customize Magento initialization parameters
For example: "MAGE_MODE=developer&MAGE_DIRS[base][path]=/var/www/example.com&MAGE_DIRS[cache][path]=/var/tmp/cache"

### maintenance:disable

Disables maintenance mode

Options:

- --ip=IP                                    Allowed IP addresses (use 'none' to clear allowed IP list) (multiple values allowed)
- --magento-init-params=MAGENTO-INIT-PARAMS  Add to any command to customize Magento initialization parameters
For example: "MAGE_MODE=developer&MAGE_DIRS[base][path]=/var/www/example.com&MAGE_DIRS[cache][path]=/var/tmp/cache"
  
### maintenance:enable

Enables maintenance mode

Options:

- --ip=IP                                    Allowed IP addresses (use 'none' to clear allowed IP list) (multiple values allowed)
- --magento-init-params=MAGENTO-INIT-PARAMS  Add to any command to customize Magento initialization parameters
  For example: "MAGE_MODE=developer&MAGE_DIRS[base][path]=/var/www/example.com&MAGE_DIRS[cache][path]=/var/tmp/cache"

### maintenance:status

Displays maintenance mode status

Options:

- --magento-init-params=MAGENTO-INIT-PARAMS  Add to any command to customize Magento initialization parameters
  For example: "MAGE_MODE=developer&MAGE_DIRS[base][path]=/var/www/example.com&MAGE_DIRS[cache][path]=/var/tmp/cache"

## module

### module:config:status

Checks the modules configuration in the 'app/etc/config.php' file and reports if they are up to date or not

### module:disable

Disables specified modules

Arguments:

- module                                         Name of the module

Options:

- -f, --force                                    Bypass dependencies check
- --all                                      Disable all modules
- -c, --clear-static-content                     Clear generated static view files. Necessary, if the module(s) have static view files
- --magento-init-params=MAGENTO-INIT-PARAMS  Add to any command to customize Magento initialization parameters
- For example: "MAGE_MODE=developer&MAGE_DIRS[base][path]=/var/www/example.com&MAGE_DIRS[cache][path]=/var/tmp/cache"

### module:enable

Enables specified modules

Arguments:

- module                                         Name of the module

Options:

- -f, --force                                    Bypass dependencies check
- --all                                      Disable all modules
- -c, --clear-static-content                     Clear generated static view files. Necessary, if the module(s) have static view files
- --magento-init-params=MAGENTO-INIT-PARAMS  Add to any command to customize Magento initialization parameters
- For example: "MAGE_MODE=developer&MAGE_DIRS[base][path]=/var/www/example.com&MAGE_DIRS[cache][path]=/var/tmp/cache"

### module:status

Displays status of modules

Arguments:

- module-names                                   Optional module name

Options:

- --enabled                                  Print only enabled modules
- --disabled                                 Print only disabled modules
- --magento-init-params=MAGENTO-INIT-PARAMS  Add to any command to customize Magento initialization parameters For example: "MAGE_MODE=developer&MAGE_DIRS[base][path]=/var/www/example.com&MAGE_DIRS[cache][path]=/var/tmp/cache"

### module:uninstall

Uninstalls modules installed by composer

Arguments:

- module                                         Name of the module

Options:

- -r, --remove-data                              Remove data installed by module(s)
- --backup-code                              Take code and configuration files backup (excluding temporary files)
- --backup-media                             Take media backup
- --backup-db                                Take complete database backup
- --non-composer                             All modules, that will be past here will be non composer based
- -c, --clear-static-content                     Clear generated static view files. Necessary, if the module(s) have static view files
- --magento-init-params=MAGENTO-INIT-PARAMS  Add to any command to customize Magento initialization parameters
For example: "MAGE_MODE=developer&MAGE_DIRS[base][path]=/var/www/example.com&MAGE_DIRS[cache][path]=/var/tmp/cache"

## queue

### queue:consumers:list

List of MessageQueue consumers

### queue:consumers:start

Start MessageQueue consumer

Arguments:

- consumer                             The name of the consumer to be started.

Options:

- --max-messages=MAX-MESSAGES      The number of messages to be processed by the consumer before process termination. If not specified - terminate after processing all queued messages.
- --batch-size=BATCH-SIZE          The number of messages per batch. Applicable for the batch consumer only.
- --area-code=AREA-CODE            The preferred area (global, adminhtml, etc...) default is global.
- --single-thread                  This option prevents running multiple copies of one consumer simultaneously.
- --multi-process[=MULTI-PROCESS]  The number of processes per consumer.
- --pid-file-path=PID-FILE-PATH    The file path for saving PID (This option is deprecated, use --single-thread instead)

Help:
This command starts MessageQueue consumer by its name.

To start consumer which will process all queued messages and terminate execution:

      bin/magento queue:consumers:start someConsumer

To specify the number of messages which should be processed by consumer before its termination:

      bin/magento queue:consumers:start someConsumer --max-messages=50

To specify the number of messages per batch for the batch consumer:

      bin/magento queue:consumers:start someConsumer --batch-size=500

To specify the preferred area:

      bin/magento queue:consumers:start someConsumer --area-code='adminhtml'

To do not run multiple copies of one consumer simultaneously:

      bin/magento queue:consumers:start someConsumer --single-thread

To save PID enter path (This option is deprecated, use --single-thread instead):

      bin/magento queue:consumers:start someConsumer --pid-file-path='/var/someConsumer.pid'

To define the number of processes per consumer:

      bin/magento queue:consumers:start someConsumer --multi-process=4

## setup

### setup:config:set

Creates or modifies the deployment configuration

### setup:install

Installs the Magento application

### setup:static-content:deploy

Deploys static view files

Arguments:

- languages                                      Space-separated list of ISO-639 language codes for which to output static view files.

Options:

- -f, --force                                    Deploy files in any mode.
- -s, --strategy[=STRATEGY]                      Deploy files using specified strategy. [default: "quick"]
- -a, --area[=AREA]                              Generate files only for the specified areas. [default: ["all"]] (multiple values allowed)
- --exclude-area[=EXCLUDE-AREA]              Do not generate files for the specified areas. [default: ["none"]] (multiple values allowed)
- -t, --theme[=THEME]                            Generate static view files for only the specified themes. [default: ["all"]] (multiple values allowed)
- --exclude-theme[=EXCLUDE-THEME]            Do not generate files for the specified themes. [default: ["none"]] (multiple values allowed)
- -l, --language[=LANGUAGE]                      Generate files only for the specified languages. [default: ["all"]] (multiple values allowed)
- --exclude-language[=EXCLUDE-LANGUAGE]      Do not generate files for the specified languages. [default: ["none"]] (multiple values allowed)
- -j, --jobs[=JOBS]                              Enable parallel processing using the specified number of jobs. [default: 0]
- --max-execution-time[=MAX-EXECUTION-TIME]  The maximum expected execution time of deployment static process (in seconds). [default: 900]
- --symlink-locale                           Create symlinks for the files of those locales, which are passed for deployment, but have no customizations.
- --content-version=CONTENT-VERSION          Custom version of static content can be used if running deployment on multiple nodes to ensure that static content version is identical and caching works properly.
- --refresh-content-version-only             Refreshing the version of static content only can be used to refresh static content in browser cache and CDN cache.
- --no-javascript                            Do not deploy JavaScript files.
- --no-js-bundle                             Do not deploy JavaScript bundle files.
- --no-css                                   Do not deploy CSS files.
- --no-less                                  Do not deploy LESS files.
- --no-images                                Do not deploy images.
- --no-fonts                                 Do not deploy font files.
- --no-html                                  Do not deploy HTML files.
- --no-misc                                  Do not deploy files of other types (.md, .jbf, .csv, etc.).
- --no-html-minify                           Do not minify HTML files.
- --no-parent                                Do not compile parent themes. Supported only in quick and standard strategies.

### setup:store-config:set

Installs the store configuration. Deprecated since 2.2.0. Use config:set instead

### setup:uninstall

Uninstalls the Magento application

### setup:upgrade

Upgrades the Magento application, DB data, and schema

Options:

- --keep-generated                             Prevents generated files from being deleted.
We discourage using this option except when deploying to production.
Consult your system integrator or administrator for more information.
- --convert-old-scripts[=CONVERT-OLD-SCRIPTS]  Allows to convert old scripts (InstallSchema, UpgradeSchema) to db_schema.xml format [default: false]
- --safe-mode[=SAFE-MODE]                      Safe installation of Magento with dumps on destructive operations, like column removal
- --data-restore[=DATA-RESTORE]                Restore removed data from dumps
- --dry-run[=DRY-RUN]                          Magento Installation will be run in dry-run mode [default: false]
- --magento-init-params=MAGENTO-INIT-PARAMS    Add to any command to customize Magento initialization parameters
For example: "MAGE_MODE=developer&MAGE_DIRS[base][path]=/var/www/example.com&MAGE_DIRS[cache][path]=/var/tmp/cache"


## store

### store:list

Displays the list of stores

### store:website:list

Displays the list of websites

## theme

### theme:uninstall

Uninstalls theme

Arguments:

- theme                       Path of the theme. Theme path should be specified as full path which is area/vendor/name. For example, frontend/Magento/blank

Options:

- --backup-code           Take code backup (excluding temporary files)
- -c, --clear-static-content  Clear generated static view files.
