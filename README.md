#lightCheckout 1.1
##Lightchekout is a jQuery plugin that simplify your address form reducing your form fields and increase conversion rate. It hide address, city, province and zipcode fields and replace them with Google Places Autocompleter, that autofill the form.

###Why should I use lightCheckout?
* It makes your address forms:
* Faster
* Easier
* More User Friendly
* Reduce Human Errors
* Helps users to fill form fields
* Suggests users all addresses informations
* Moz, Ms, Webkit Tested
* Easy to Customize

For complete documentation, tons of examples, and a good time, visit:

[http://www.lightcheckout.com](http://www.lightcheckout.com)

Written by: Claudio Sperti

###License
Released under the MIT license - http://opensource.org/licenses/MIT

Let's get on with it!

##Installation

###Step 1: Link required files

First and most important, the jQuery library needs to be included. Next, download the package from this site and link the lightCheckout CSS file and the lightCheckout Javascript file.

```html
<!-- jQuery library (served from Google) -->
<script src="//ajax.googleapis.com/ajax/libs/jquery/1.8.2/jquery.min.js"></script>
<!-- lightCheckout Javascript file -->
<script src="/js/lightCheckout.min.js"></script>
<!-- lightCheckout CSS file -->
<link href="/css/lightCheckout.css" rel="stylesheet" />
```

###Step 2: Starting HTML DOM

Initially your page contains a form (or just a fields wrapper) 

```html
<form class="addressForm">
   <div class="name">
      <input name="name" id="name" type="text" />
   </div>
   <div class="surname">
      <input name="surname" id="surname" type="text" />
   </div>
   <div class="address">
      <input name="address" id="address" type="text" />
   </div>
   <div class="city">
      <input name="city" id="city" type="text" />
   </div>
   <div class="zipcode">
      <input name="zipcode" id="zipcode" type="text" />
   </div>
   <div class="province">
      <select name="province" id="province" >
          <option value="NY">New York</option>
          <option value="CA">California</option>
         <option value="...">...</option>
      </select>
   </div>
   <div class="submit">
      <input type="submit" value="Continue">
   </div>
</form>
```

###Step 3: Create an options js object and Call LightChekout

Before you have to create a js var that contains basic lightCheckout options:

* inputWrapper // DOM element that wraps each input or select field
* address // address input field
* city // city input field
* province // province input field
* zip // zip code input field

Then call .lightChekout() on your <form> or wrapper. Note that the call must be made inside of a $(document).ready() call, or the plugin will not work!

```javascript
$(document).ready(function(){
	var options = {
		inputWrapper: 'div',
		address: '#address',
		city: '#city',
		province: '#province',
		zip: '#zipcode'
	};
	$('.addressForm').lightChekout(options);
});
```

##Configuration options

###General

**inputWrapper**
Selector of input wrapper
```
default: 'div'
options: string, any jQuery selector
```

**autocomplete**
Selector of autocomplete input, if you created it manually
```
default: null
options: string, any jQuery selector
```

**address**
Selector of address input
```
default: '.address'
options: string, any jQuery selector
```

**city**
Selector of city input
```
default: '.city'
options: string, any jQuery selector
```

**province**
Selector of province input
```
default: '.province'
options: string, any jQuery selector
```

**zip**
Selector of zip input
```
default: '.zip'
options: string, any jQuery selector
```

**shortProvince**
Boolean, choose if province must be set with short name or long name (ex. Long Name: "California", Short name: "CA")
```
default: true
options: true, false
```

**noNumberError**
Error to show when users not set street number in address input
```
default: 'Please, insert also street number.'
options: string, any message you want to show as error
```

**language**
Language of Google Places libraries
```
default: 'en'
options: string, one of supported language from this list: https://developers.google.com/maps/faq#languagesupport
```

###Events

**setField**
When an address is set, you can override common fill of inputs
```
default: function ($input, value) {
				$input.val(value);
			}
options: function ($input, value) { // your code here }
arguments:
  $input: input element that must be changed
  value: new value of the input
```
