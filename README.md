Based off the fantastic class by Sam Vermette on [SVProgressHUD](https://github.com/samvermette/SVProgressHUD). nsProgress aims to fill the gap by allowing websites and specifically phonegap apps a cross platform way of showing progress via a HUD. This plugin is written for jQuery so requires this to work (written with 1.8.2).

As with SVProgressHUD, the success and error icons are from [Glyphish](http://glyphish.com/).

## Simple Usage
To get started, place a div in your source and call the plugin on it to initialise.

```
<div id="progress_modal"></div> 

<script>
    $(document).ready(function() {

        // Default Settings
        $('#progress_modal').nsProgress();

        // Custom Settings
        $('#progress_modal').nsProgress({
            img_path: 'js/plugins/nsProgress/img'
        });

    });
</script>
```

You are now ready to call methods on the plugin to display, change and hide the HUD.

```
<script>
    $(document).ready(function() {

        $('#progress_modal').nsProgress();
        $('#progress_modal').nsProgress('showSuccessWithStatusAndMaskType', 'It Worked!', 'black');

    });
</script>
```

Which will display something like this:

![Demo Result](http://f.cl.ly/items/3c110E0u2Z3r2n353E0s/Image%202012.10.04%2014:10:43.png)

## HUD Options
There are a few options that you can pass to choose the HUD Mask style, they are

<table>
    <tr>
        <td>'none'</td>
        <td>allow user interactions, don't dim background UI (default)</td>
    </tr>
    <tr>
        <td>'clear'</td>
        <td>disable user interactions, don't dim background UI</td>
    </tr>
    <tr>
        <td>'black'</td>
        <td>disable user interactions, dim background UI with 50% translucent black (my favourite)</td>
    </tr>
</table>

## Methods Available
I've tried to cover every possible combination, they should be self explanitory!

```
$('#progress_modal').nsProgress('show');
$('#progress_modal').nsProgress('showWithMaskType', 'none');
$('#progress_modal').nsProgress('showWithStatus', 'Loading&hellip;');
$('#progress_modal').nsProgress('showWithStatusAndMaskType', 'Loading&hellip;', 'none');
$('#progress_modal').nsProgress('showWithImage', 'nsLoader.gif');
$('#progress_modal').nsProgress('showSuccessWithStatus', 'Error');
$('#progress_modal').nsProgress('showErrorWithStatus', 'Success');
$('#progress_modal').nsProgress('showSuccessWithStatusAndMaskType', 'Success', 'none');
$('#progress_modal').nsProgress('showErrorWithStatusAndMaskType', 'Error', 'none');
$('#progress_modal').nsProgress('showWithImageAndStatus', 'nsLoader.gif', 'Loading&hellip;');
$('#progress_modal').nsProgress('showWithImageAndMaskType', 'nsLoader.gif', 'none');
$('#progress_modal').nsProgress('showWithImageAndStatusAndMaskType', 'nsLoader.gif', 'Loading&hellip;', 'none');
$('#progress_modal').nsProgress('dismiss');

```

## TODO
Feel free to fork and add any of these if I don't get round to doing them :)

* Delayed dissmissal message like SVProgressHUD has (eg, SVProgressHUD dismissWithError:@"Error Connecting")
* Swap out for retina if the @2x images exist
* More config settings