const http = require('http');

const server = http.createServer((req, res) => {
    let data = '';
    req.on('data', chunk => {
        data += chunk;
    });
    req.on('end', () => {
        console.log('Полученные данные:', data);
        res.end('Данные получены');
    });
});

server.listen(3000, () => {
    console.log('Сервер запущен на http://localhost:3000');
});
