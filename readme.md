
Midtrans Payment API Postman Collection
=====================================

Midtrans&nbsp; :heart: Postman!

## Description

This repository contains [Postman](https://www.getpostman.com) collection for various payment API call to [Midtrans](https://midtrans.com) Payment API.

API covered:
* [SNAP API](http://snap-docs.midtrans.com)
* [Core API](http://api-docs.midtrans.com)

## Usage Instruction

1. Download and open [Postman](https://www.getpostman.com)
2.  Import:
    - Use this link: https://www.getpostman.com/collections/af068be08b5d1a422796 , or
    - Clone or [download](/archive/master.zip) this repository, then import postman collections from `MidtransPaymentAPI.postman_collection` file.
3. [Register to Midtrans](https://dashboard.midtrans.com/register)
4. [Login](http://dashboard.midtrans.com) to Midtrans, switch to **Sandbox**, go to menu `Settings > Access Keys`. Copy your **Server Key**
5. In Postman, open **Midtrans Payment API** then choose one request you want to try, click on `Authorization` tab (beside Headers tab)
6. Select **Type** as `Basic Auth`, fill **Username** with your **Server Key** (looks like this `VT-server-xxxxxx`). Leave **Password** field blank, click **Update Request**
7. Now you can `save` then click `send` the request. You will get server response.

> ![Authorization Config](https://cloud.githubusercontent.com/assets/13027142/20592019/1e6ab9ec-b25e-11e6-9285-c68fef6c538c.png)


## Specific Usage

###### *You need to download/clone this repo to your local to use these:*

### SNAP - Snap Popup Viewer

If you are testing `Snap transaction token request` you will get response like:
```
{ "token": "bffb82ff-f8bb-4651-86b0-0c2316b77c0a" }
```
To see how that token works, you can open file `../snap-opener/index.html` in your web browser to preview the SNAP payment page.
- Tips: you can also append snap token like this in url `../snap-opener/index.html?snap_token=bffb82ff-f8bb-4651-86b0-0c2316b77c0a&is_production=false`

You can also edit file `snap/index.html` and insert your own token to the HTML, then open in web browser.

###### *This file is for snap token viewer only, you should not use this for integration reference, for front-end integration sample, see below section*

### SNAP - Snap Front-End Integration Example

For real example on how you can use Snap token in your website front-end, you can see sample minimum implementation here:
`../sample-frontend/index.html`

> Edit the file and insert `<Your-Client-Key-Here>` with your client key.

### Core API - Credit Card Get Token & 3DS Authenticate Example

To get credit card token for Core API Credit Card charge process, here's [sample implementation that you can check](https://github.com/Midtrans/midtrans-python-client/blob/master/examples/flask_app/templates/simple_core_api_checkout.html). (mandiri clickpay also need get token process).

## Production Mode

All endpoint used in this postman collection is for `sandbox transaction`, to switch to `production` change endpoint URL from:

`https://api.sandbox.midtrans.com/../..`

to

`https://api.midtrans.com/../..`

(Just remove the `sandbox.` from url)

## Troubleshooting

If you get error
```
{
  "error_messages": [
    "Access denied due to unauthorized transaction, please check client or server key",
    "Visit https://snap-docs.midtrans.com/#request-headers for more details"
  ]
}
```
- Please make sure you do step 4-7 properly like instructed in **[Usage Instruction](#usage-instruction)** section.
- Please make sure you are using correct **Server Key** (Serverkey for sandbox & production are different).

### Changelog

15/11/2018
- Add sample collection for flow recurring Credit Cards.
- Add a list of information and contacts to help understand the use of the Midtrans product API.

25/01/2018
- Add gopay & danamon online banking example.
- Change mandiri clickpay request, according to docs.
- Change sample customer email.

12/04/2019
- Restructurize
- Sync with current API docs
- Update to 3DS new flow

### Get Help

* [Midtrans Profile&nbsp;](https://www.midtrans.com)
* [Midtrans Registration](https://dashboard.midtrans.com/register)
* [General Documentation Midtrans](http://docs.midtrans.com)
* [SNAP documentation](http://snap-docs.midtrans.com)
* [Core API documentation](http://api-docs.midtrans.com)
* [Mobile Documentation Product Midtrans](http://mobile-docs.midtrans.com/)
* Can't find answer you looking for? email to Technical Support Team Midtrans [support@midtrans.com](mailto:support@midtrans.com)
