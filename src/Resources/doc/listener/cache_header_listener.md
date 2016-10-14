#Cache Header Listener
This listener sets the cachemeta in the response header.

**This listener is deprecated. Use http://symfony.com/doc/current/bundles/SensioFrameworkExtraBundle/annotations/cache.html instead.**

## Configuration
```yaml
    # app/config/config*.yml
    
    ibrows_rest:
        caches:
            cache1: 
                type: private
                max_age: 600
        listener:
            cache:
                enabled: false
```
 - The `type` string defines the type of the cache. The `type` have to be `private` or `public`. 
 - The `max_age` integer describes the lifetime of the cache.
`no-cache` and `no-store` are currently not supported
 - `enabled` - Enable / Disable the listener (default: `false`)

These caches can later be accessed via its name. The name have to be configured in the `View` annotation on the action

## Controller
```php
    use Ibrows\RestBundle\Annotation as IbrowsAPI;

     /**
     * @IbrowsAPI\View(
     *     serializerGroups={ "car_detail" },
     *     cachePolicyName="cache1"
     * )
     */
```