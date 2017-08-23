HncImageBundle
==================

The **HncImageBundle** adds support for various image manipulation functions in Symfony
It uses the [Intervention/image](https://github.com/Intervention/image) library in backend.

## Installation

First, open a command console, enter your project directory and execute the following command to download the latest version of this bundle:

```
composer require hnc/image-bundle dev-master
```

Then add the bundle to your kernel:
```php
class AppKernel extends Kernel
{
    public function registerBundles()
    {
        $bundles = [
            // ...

            new Hnc\ImageBundle\HncImageBundle(),
        ];

        // ...
    }
}
```

## What does this bundle?

It provides rich sets of functions for image manipulation. Please see API available at [Intervention Image](http://image.intervention.io/).

## Use the bundle

To create resized image in your controllers:

```php
namespace AppBundle\Controller;

use Sensio\Bundle\FrameworkExtraBundle\Configuration\Route;
use Symfony\Bundle\FrameworkBundle\Controller\Controller;
use Symfony\Component\HttpFoundation\Request;

class DefaultController extends Controller
{
    /**
     * @Route("/", name="homepage")
     */
    public function indexAction(Request $request)
    {
        $this->get('im')
            ->make('input.jpg')
            ->resize(800, 600)
            ->save('output.jpg');
    }
}```
## License

This bundle is released under the MIT license.