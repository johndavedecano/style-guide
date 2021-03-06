# Templates (blade, smarty, twig…)

Please refer to [Laravel “Blade Templates” article](http://laravel.com/docs/5.1/blade)
for style–guides about Blade templates.


## Addendum

### Control Structures

As decided [in this issue](https://github.com/juwai/juwai-admin/issues/394#event-437311821), the following code…

```blade
<div>
    @if (count($records) === 1)
        <div>
            …
        </div>
    @endif
</div>
```
…should be written like so:

```blade
<div>
    @if (count($records) === 1)
    <div>
        …
    </div>
    @endif
</div>
```

In case of nested control structures and loops, align the markup with the closest template control:
```blade
<div>
    @if (isset($userProfile)
        @for ($i = 0; $i < 10; $i++)
        <p>User {{ $i }} […]</p>
        @endfor
    @endif
</div
```


### PHP in templates

If having the logic outside the template makes code way more complicated, then:
- ​**either**​ there is a problem in the PHP file (controller, composer…) and we can refactor the code,
- ​**or**​ put the logic in the template, ​**and**​ leave a comment about what prevents the logic to be outside of the template.
