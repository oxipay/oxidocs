<h1>Setup on Magento 2</h1>

You can install Oxipay on your site by manually copying plugin files across into your store's webserver. Use the same instructions to upgrade your existing plugin to a newer release.

## Supported Tech Stacks

Oxipay has been developed and tested against the following Magento tech stacks:

<table>
    <tr><td>Magento Version</td><td>Operating System</td><td>SQL</td><td>PHP Version</td><td>Web Server</td><tr>
    <tr><td>Magento 2.1.5</td><td>Red Hat/Fedora</td><td></td><td>MariaDB 10.0.24</td><td>nginx 1.10.2</td><tr>
</table>

# Plugin Installation

<div class="panel">
  You will need your <b>Merchant Number</b> and an <b>Encryption Key</b> handy before continuing with the installation.
</div>

1 - Download the Oxipay plugin from [github.com/oxipay/oxipay-magento-2.x/releases](https://github.com/oxipay/oxipay-magento-2.x/releases).

2 - Unzip it then copy the inner `Oxipay` folder into the `MAGENTO_DIR/app/code` directory.

<div class="panel">
  If the <code>code</code> folder doesn't exist in the <code>app</code> directory, you will need to create it manually.
</div>

3 - Change directory into `MAGENTO_DIR/bin`. This will make the `magento` utility available.

4 - Run the following command to enable existing plugins including Oxipay
<br>
`magento setup:upgrade`

<div class="panel">
  Depending on your Magento 2 tech stack, you might have to use the <code>php</code> prefix: <code>php magento setup:upgrade</code>
</div>

5 - You should see `Module 'Oxipay_OxipayPaymentGateway'` in the output of the command.

6 - Flush the Magento Cache by navigating to **Settings** -> **Cache Management** -> **Flush Magento Cache**.

7 - You should now be able to see the Oxipay plugin setting page by navigating to **Stores** -> **Configuration** -> **Sales** -> **Payment Methods** similar to screen below:

![4.png](/img/platforms/magento_2/4.png)