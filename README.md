# PHP Server

Package to manage the PHP built-in server from node.

## Usage

```js
const PHPServer = require('php-server');

const server = new PHPServer();

server.run(); // http://localhost:8000
```

## Configuration

Name | Default | Description
-----|---------|------------
`php` | `php` | The php command file
`host` | `localhost` | The server's host
`port` | `8000` | The port used
`directory` | `null` | The document root. By default is the current working directory
`script` | `null` | The "router" script
`directives` | `{}` | An object with the custom PHP directives
`config` | `null` | The path of a custom php.ini file

Example:

```js
const PHPServer = require('php-server');

const server = new PHPServer({
	port: 3000,
	directives: {
		display_errors: 0,
        expose_php: 0
	}
});

server.run();
```

## Use with gulp

```js
gulp.task('php-server', () => {
    const server = new PHPServer({
        directory: 'public',
        script: 'public/index.php'
    });

    server.run();
});
```

