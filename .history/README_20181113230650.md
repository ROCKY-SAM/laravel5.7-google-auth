

Copy .env.example to .env:

cp -a .env.example .env

Generate a key:

php artisan key:generate

Only then run:

php artisan serve


//Socialite::driver('google')->stateless()->user()

#error
InvalidStateException in AbstractProvider.php line 182
The Solution

    Go to your www root, check the laravel file config/session.php
    Check session Session Cookie Domain The default configuration is 'domain' => null, I made a change to 'domain' => 'mysite.com'.
    After 'php artisan cache:clear' and 'composer dump-autoload', I can login with no issue from both www.mysite.com and mysite.com
