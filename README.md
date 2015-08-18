#Silverstripe Vend API integration
This is basically a wrapper for the [VendAPI package](https://github.com/brucealdridge/VendAPI) by @brucealdridge for Silverstripe.

The main difference is implementation for OAuth2 and refresh tokens.
##Requires
- Silverstripe 3.1
- The [vendapi/vendapi](https://github.com/brucealdridge/VendAPI) package
 
##Install

using Composer: `composer require heyday/silverstripe-vend:dev/master`

##Setup

you need to sign up for a Vend developer account.

When you have done so, set your details in a yml config file under `VendAPI`.

eg `mysite/_config/vend.yml` :

```
################
###VEND SETUP###
################

VendAPI:
  clientID: g6ohGHJgJHKtuyfUTYfjVjhGhfTUYfTU
  clientSecret: iyGFktyFKUYlguKHkjHUHUiGHKuHGKj
  redirectURI: admin/vend/authorise

```

After a `dev/build` and a `flush` you should have a new Menu called `Vend Admin` where the next steps of the setup are done.

##Implementation

To use you just need to use the `Heyday\Vend\SilverStripe\Connection` and follow the docs of the [VendAPI package](https://github.com/brucealdridge/VendAPI) for the other methods.


eg:

```
$connection = new Heyday\Vend\SilverStripe\Connection();
$products = $connection->getProducts();
```        
  