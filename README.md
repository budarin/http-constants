# @budarin/http-constants

TypeScript библиотека с константами для HTTP протокола.

## Установка

```bash
npm install @budarin/http-constants
# или
pnpm add @budarin/http-constants
```

## Использование

### Импорт всех констант

```typescript
import * from '@budarin/http-constants';
```

### Импорт отдельных модулей

```typescript
// HTTP методы
import { GET, POST, PUT, DELETE } from '@budarin/http-constants/methods';

// HTTP статус коды
import {
    OK,
    NOT_FOUND,
    INTERNAL_SERVER_ERROR,
} from '@budarin/http-constants/statuses';

// HTTP заголовки
import { CONTENT_TYPE, AUTHORIZATION } from '@budarin/http-constants/headers';

// Content Types
import {
    APPLICATION_JSON,
    TEXT_HTML,
} from '@budarin/http-constants/content-types';

// Service Worker константы
import {
    SW_EVENT_INSTALL,
    SW_STATE_ACTIVATED,
} from '@budarin/http-constants/service-worker';
```

## Доступные константы

### HTTP методы (`methods`)

- `GET`, `POST`, `PUT`, `DELETE`, `PATCH`, `OPTIONS`, `HEAD`

### HTTP статус коды (`statuses`)

- **1xx**: `CONTINUE`, `SWITCHING_PROTOCOLS`
- **2xx**: `OK`, `CREATED`, `ACCEPTED`, `NO_CONTENT`
- **3xx**: `MOVED_PERMANENTLY`, `FOUND`, `NOT_MODIFIED`
- **4xx**: `BAD_REQUEST`, `UNAUTHORIZED`, `FORBIDDEN`, `NOT_FOUND`, `METHOD_NOT_ALLOWED`
- **5xx**: `INTERNAL_SERVER_ERROR`, `NOT_IMPLEMENTED`, `BAD_GATEWAY`, `SERVICE_UNAVAILABLE`

### HTTP заголовки (`headers`)

- `CONTENT_TYPE`, `CONTENT_LENGTH`, `AUTHORIZATION`, `ACCEPT`, `USER_AGENT`, `CACHE_CONTROL`, `RANGE`, `CONTENT_RANGE`

### Content Types (`content-types`)

- `APPLICATION_JSON`, `APPLICATION_X_WWW_FORM_URLENCODED`, `MULTIPART_FORM_DATA`, `TEXT_PLAIN`, `TEXT_HTML`

### Service Worker (`service-worker`)

- **События**: `SW_EVENT_INSTALL`, `SW_EVENT_ACTIVATE`, `SW_EVENT_FETCH`, и др.
- **Состояния**: `SW_STATE_ACTIVATED`, `SW_STATE_INSTALLING`, и др.
- **Команды**: `PAGE_RELOAD`, `SKIP_WAITING`, и др.

## Пример

```typescript
import { GET, POST } from '@budarin/http-constants/methods';
import { OK, NOT_FOUND } from '@budarin/http-constants/statuses';
import { APPLICATION_JSON } from '@budarin/http-constants/content-types';

// Использование в Express.js
app.get('/api/users', (req, res) => {
    if (req.method === GET) {
        res.status(OK).json({ users: [] });
    }
});

// Использование в fetch
fetch('/api/data', {
    method: POST,
    headers: {
        'Content-Type': APPLICATION_JSON,
    },
});
```

## Лицензия

MIT
