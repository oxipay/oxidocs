<h1>Setup on Magento 2</h1>

You can install %product_name% plugin by manually copying plugin files across into your store's webserver. <br>
Use the same instructions to upgrade your existing plugin to a newer release.

## Supported Tech Stacks

%product_name% has been tested against the following tech stacks:

|Magento Version| Operating System  | SQL         | PHP Version | Web Server  |
|---------------|-------------------|-------------|-------------|-------------|
|Magento 2.1.5  |Ubuntu 14.04.5 LTS |MySQL 5.7.17 |7.0.16       |Apache 2.4.25|


## Plugin Installation

<div class="panel">
  You will need your <b>Merchant Number</b> and an <b>Encryption Key</b> handy before continuing with the installation.
</div>

1 - Download the %product_name% plugin from [github.com/Certegy/certegy-ezipay-magento-2.x/releases](https://github.com/Certegy/certegy-ezipay-magento-2.x/releases).

2 - Unzip it then copy the inner `%product_name%` folder into the `MAGENTO_DIR/app/code` directory on your webserver. If the <code>code</code> folder doesn't exist, then create it manually.

3 - Change directory into `MAGENTO_DIR/bin` to make the `magento` utility available.

4 - Run `magento setup:upgrade`. This will auto-enable %product_name% as part of `setup:upgrade`. You should see `Module '%product_name%_PaymentGateway'` in the output of the command.
<br>

<div class="panel">
  Depending on your tech stack, you might have to use the <code>php</code> prefix (<code>php magento setup:upgrade</code>) when running the various <code>magento</code> commands.
</div>

5 - Flush Magento's Cache by navigating to **Settings** -> **Cache Management** -> **Flush Magento Cache**. Alternatively, you can run <code>MAGENTO_DIR/bin/magento cache:flush</code> from the command line.

6 - Run `setup:static-conent:deploy` to avoid generated HTML referring to javascript/css that haven't been added to the list of compiled/minified assets which can break your store's front-end/admin panel.

7 - To view %product_name%'s settings page, navigate to **Stores** -> **Configuration** -> **Sales** -> **Payment Methods**.