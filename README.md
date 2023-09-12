for create project
composer create-project laravel/laravel first-laravel9

run below command 
composer require laravel/ui
php artisan ui bootstrap --auth
npm install
npm install --save-dev vite laravel-vite-plugin
npm install lodash

change vite.config file
import { defineConfig } from 'vite';
import laravel from 'laravel-vite-plugin';
import path from 'path'

export default defineConfig({
    plugins: [
        laravel([
            'resources/js/app.js',
        ]),
    ],
    resolve: {
        alias: {
            '~bootstrap': path.resolve(__dirname, 'node_modules/bootstrap'),
        }
    },
    css: {
        preprocessorOptions: {
          scss: {
            additionalData: `@import "resources/sass/custome.scss";`, // Include your custom SCSS file
          },
        },
      },
});


update bootstrap.js
import loadash from 'lodash'
window._ = loadash


import * as Popper from '@popperjs/core'
window.Popper = Popper

import 'bootstrap'


/**
 * We'll load the axios HTTP library which allows us to easily issue requests
 * to our Laravel back-end. This library automatically handles sending the
 * CSRF token as a header based on the value of the "XSRF" token cookie.
 */

import axios from 'axios'
window.axios = axios

window.axios.defaults.headers.common['X-Requested-With'] = 'XMLHttpRequest';

/**
 * Echo exposes an expressive API for subscribing to channels and listening
 * for events that are broadcast by Laravel. Echo and event broadcasting
 * allows your team to easily build robust real-time web applications.
 */

// import Echo from 'laravel-echo';

// window.Pusher = require('pusher-js');

// window.Echo = new Echo({
//     broadcaster: 'pusher',
//     key: process.env.MIX_PUSHER_APP_KEY,
//     cluster: process.env.MIX_PUSHER_APP_CLUSTER,
//     forceTLS: true
// });


change app.js
import './bootstrap';

import '../sass/app.scss'

add blade file 
@vite(['resources/js/app.js'])

npm run build




