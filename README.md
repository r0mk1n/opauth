![Opauth](https://github.com/uzyn/opauth.org/raw/master/images/opauth-logo-300px-transparent.png)
=================================
Opauth is a multi-provider authentication framework for PHP, inspired by [OmniAuth for Ruby](https://github.com/intridea/omniauth).

Opauth enables PHP applications to do *user authentication* with ease.

Try out Opauth for yourself at http://opauth.org

[![Build Status](https://secure.travis-ci.org/uzyn/opauth.png?branch=master)](http://travis-ci.org/uzyn/opauth)

What is Opauth?
---------------
Opauth provides a standardized method for PHP applications to interface with authentication providers. 

Opauth as a framework provides a set of API that allows developers to [create strategies](https://github.com/uzyn/opauth/wiki/Strategy-Contribution-Guide) that work in a predictable manner across PHP frameworks and applications.

Opauth works well with other PHP applications & frameworks. It is currently supported on:

- [vanilla (plain) PHP applications](https://github.com/uzyn/opauth/tree/master/example) *(of course)*
- [CakePHP](https://github.com/uzyn/cakephp-opauth) (maintained by [uzyn](https://github.com/uzyn))
- [CodeIgniter](https://github.com/destinomultimedia/ci_opauth) (maintained by [destinomultimedia](https://github.com/destinomultimedia))
- [CodeIgniter](https://github.com/mcatm/Opauth-Plugin-for-Codeigniter) (maintained by [mcatm](https://github.com/mcatm))
- [FuelPHP](https://github.com/andreoav/fuel-opauth) (maintained by [andreoav](https://github.com/andreoav/))
- [Yii Framework](https://github.com/kahwee/yii-opauth) (maintained by [kahwee](https://github.com/kahwee))
- and more to come.  

If your PHP framework of choice is not yet listed, you can still use Opauth like you would a normal PHP component (class).

Quick start
-----------
Guide on how to run the bundled example.

1. Set `DocumentRoot` of your web server to `example/`.  
   (Opauth can be instantiated in your own PHP app, but we will leave that out of this quick start guide)

2. Configure Opauth.

   First, make a copy of opauth config's file by copying or renaming  
   `opauth.conf.php.default` to `opauth.conf.php`.

   Open up `opauth.conf.php` and make the necessary changes.

3. Install some [Opauth strategies](https://github.com/uzyn/opauth/wiki/List-of-strategies).  
   Place the strategy files in `lib/Opauth/Strategy/`.  

   For this example, we recommend that you start with [Opauth-Facebook](https://github.com/uzyn/opauth-facebook):

   i. [Download the strategy files](https://github.com/uzyn/opauth-facebook/zipball/master) and place them at `lib/Opauth/Strategy/Facebook/`.

   ii. Follow the steps at [Opauth-Facebook's README](https://github.com/uzyn/opauth-facebook/blob/master/README.md) to set up your Faceobok app.

   iii. Add the following at `opauth.conf.php` under `Strategy` as such:  

```php
<?php
'Strategy' => array(  
    // Define strategies here.

    'Facebook' => array(
        'app_id' => 'YOUR APP ID',
        'app_secret' => 'YOUR APP SECRET'
    ),
);
```

Finally, send user to `http://localhost/facebook` to authenticate.


Check out [the wiki](https://github.com/uzyn/opauth/wiki) for more in-depth details, especially on how to use Opauth with your own PHP application.

Available strategies
--------------------
A strategy is a set of instructions that interfaces with respective authentication providers and relays it back to Opauth.

Provider-specific:

<table>
<tr>
	<th>Strategy</th>
	<th>Maintained by</th>
</tr>
<tr>
	<td><img src="http://g.etfv.co/http://facebook.com" alt="Facebook">&nbsp;&nbsp;
		<a href="https://github.com/uzyn/opauth-facebook">Facebook</a></td>
	<td>uzyn</td>
</tr>
<tr>
	<td><img src="http://g.etfv.co/http://google.com" alt="Google">&nbsp;&nbsp;
		<a href="https://github.com/uzyn/opauth-google">Google</a></td>
	<td>uzyn</td>
</tr>
<tr>
	<td><img src="http://g.etfv.co/http://instagram.com" alt="Instagram">&nbsp;&nbsp;
		<a href="https://github.com/muhdazrain/opauth-instagram">Instagram</a></td>
	<td>muhdazrain</td>
</tr>
<tr>
	<td><img src="http://g.etfv.co/http://linkedin.com" alt="LinkedIn">&nbsp;&nbsp;
		<a href="https://github.com/uzyn/opauth-linkedin">LinkedIn</a></td>
	<td>uzyn</td>
</tr>
<tr>
	<td><img src="http://g.etfv.co/http://mixi.co.jp" alt="mixi">&nbsp;&nbsp;
		<a href="https://github.com/ritou/opauth-mixi">mixi</a></td>
	<td>ritou</td>
</tr>
<tr>
	<td><img src="http://g.etfv.co/http://openid.net" alt="OpenID">&nbsp;&nbsp;
		<a href="https://github.com/uzyn/opauth-openid">OpenID</a></td>
	<td>uzyn</td>
</tr>
<tr>
	<td><img src="http://g.etfv.co/http://twitter.com" alt="Twitter">&nbsp;&nbsp;
		<a href="https://github.com/uzyn/opauth-twitter">Twitter</a></td>
	<td>uzyn</td>
</tr>

</table>

Generic strategy: [OAuth](https://github.com/uzyn/opauth-oauth)

See [wiki's list of strategies](https://github.com/uzyn/opauth/wiki/List-of-strategies) for an updated list of Opauth strategies or to make requests.  Also, refer to [strategy contribution guide](https://github.com/uzyn/opauth/wiki/Strategy-contribution-guide) if you would like to contribute a strategy.

Requirements
-------------
PHP 5 (>= 5.2)

Contribute
----------
Opauth needs your contributions, especially the following:

- More strategies  
  Refer to [wiki](https://github.com/uzyn/opauth/wiki) for contribution guide and inform us when your work is ready.

- Plugins for more PHP frameworks and CMSes  
  eg. CodeIgniter, Symfony, WordPress, Drupal, etc.

- Guides & tutorials  
  On how to implement Opauth on CakePHP app, etc.

- Unit testing  
  Coverage is only average at the moment.


Issues & questions
-------------------
- Issues: [Github Issues](https://github.com/uzyn/opauth/issues)  
- Discussion group: [Google Groups](https://groups.google.com/group/opauth)
- Twitter: [@uzyn](http://twitter.com/uzyn)  
- Email me: chua@uzyn.com  
- IRC: **#opauth** on [Freenode](http://webchat.freenode.net/?channels=opauth&uio=d4)

<p>Used Opauth in your project? Let us know!</p>

Changelog
---------
###v0.4.0 (10 June 2012)
- `mapProfile()` and `clientGet()` for OpauthStrategy class.

###v0.3.0 (30 May 2012)
- Some unit testing
- More consistent naming of Strategy's internal properties
- Smarter loading of strategy, able to make a few guesses on where the class file might be at.

###v0.2.0 (23 May 2012)
- Opauth is now Composer compatible and listed on [Packagist](http://packagist.org/packages/opauth/opauth)
    - Opauth now supports autoloaders
    - If a strategy is not autoloaded, Opauth falls back and searches for it at `strategy_dir` defined in config.
- Class name for strategy Foo should now be FooStrategy instead of Foo.
    - This is to reduce the likelihood of class name collision due to Opauth not requiring the use of namespace.
    - v0.1.0-type class name, ie. Foo, still works, but is now deprecated.

###v0.1.0 (22 May 2012)
- Initial release

License
---------
The MIT License  
Copyright © 2012 U-Zyn Chua (http://uzyn.com)

Footnote
---------
U-Zyn Chua is a Principal Consultant at [gladlyCode](http://gladlycode.com), a premier PHP web development firm.  
If you need consultation in web technologies and services, feel free to [talk to us](mailto:we@gladlycode.com).
