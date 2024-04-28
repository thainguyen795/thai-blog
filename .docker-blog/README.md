## Setup docker-compose
- Copy ``.forix`` into source code
- Replace your url corectly on ``.forix/.env``
- By default, pwa will connect to M2Staging, keep it as is incase you only work with PWA
- For BE DEV, if you are working with layers, you want to connect local layer, you need to adjust domains correctly with your setup on laravel and magento local and change ``LOCAL_TYPE=backend``
- Add your domains to ``/etc/hosts``

## Start
- On source root, ``cp env.template .env`` and replace content to:
  ``API_GATEWAY_URL=https://[LOCAL_PWA_DOMAIN]/graphql``
  ``NEXT_PUBLIC_API_GATEWAY_URL=$API_GATEWAY_URL``
  ``NEXT_PUBLIC_STORE_CODE=default``
  ``NEXT_PUBLIC_X_PYLOT_BACKEND=minerva_stage``
  ``NODE_TLS_REJECT_UNAUTHORIZED=0``

- ``cd .forix``
- ``docker-compose run --rm nodejs yarn install`` (first time)
- ``docker-compose up -d`` to start containers, you can be use ``docker-compose logs -f nodejs`` for detail starting.
  - We are running pwa on dev mode, the dev mode support hot-reload and built time will take a long, you have to wait a time for starting.

