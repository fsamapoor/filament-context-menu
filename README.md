# Context Menu for Filament

[![Latest Version on Packagist](https://img.shields.io/packagist/v/aymanalhattami/filament-context-menu.svg?style=flat-square)](https://packagist.org/packages/aymanalhattami/filament-context-menu)
[![GitHub Tests Action Status](https://img.shields.io/github/actions/workflow/status/aymanalhattami/filament-context-menu/run-tests.yml?branch=main&label=tests&style=flat-square)](https://github.com/aymanalhattami/filament-context-menu/actions?query=workflow%3Arun-tests+branch%3Amain)
[![GitHub Code Style Action Status](https://img.shields.io/github/actions/workflow/status/aymanalhattami/filament-context-menu/fix-php-code-styling.yml?branch=main&label=code%20style&style=flat-square)](https://github.com/aymanalhattami/filament-context-menu/actions?query=workflow%3A"Fix+PHP+code+styling"+branch%3Amain)
[![Total Downloads](https://img.shields.io/packagist/dt/aymanalhattami/filament-context-menu.svg?style=flat-square)](https://packagist.org/packages/aymanalhattami/filament-context-menu)

---
This package is used to add context menu (right click menu) for resource pages and custom pages of [Filament Admin Panel](https://filamentphp.com/).
* It uses [Filament Actions](https://filamentphp.com/docs/3.x/actions/overview) to set menu items.
* Support dark and light mode.
* Support left-to-right and right-to-left direction.
* You can set a divider between menu actions.

[Demo project](https://github.com/aymanalhattami/filament-context-menu-project)

## Installation

You can install the package via composer:

```bash
composer require aymanalhattami/filament-context-menu
```

## Usage
1. Define a ```getContextMenu``` method inside the page (resource page or custom page), the method should return an instance of ```AymanAlhattami\FilamentContextMenu\ContextMenu```
2. Use ```ContextMenu``` class to set menu actions as an array

```php
use App\Filament\Resources\UserResource\Pages\CreateUser;
use Filament\Resources\Pages\ListRecords;
use AymanAlhattami\FilamentContextMenu\ContextMenu;
use Filament\Actions\Action;

class ListUsers extends ListRecords
{
    // 
    
    public static function getContextMenu(): ContextMenu
    {
        return ContextMenu::make()
            ->actions([
                Action::make('Create user')
                    ->url(CreateUser::getUrl())
            ]);
    }
    
    // 
}
```

## More options

### Divider
Use ```AymanAlhattami\FilamentContextMenu\ContextMenuDivider``` to set divider between menu actions
```php
use App\Filament\Resources\UserResource\Pages\CreateUser;
use App\Filament\Resources\UserResource\Pages\TrashedUsers;
use Filament\Resources\Pages\ListRecords;
use AymanAlhattami\FilamentContextMenu\ContextMenu;
use Filament\Actions\Action;
use AymanAlhattami\FilamentContextMenu\ContextMenuDivider;

class ListUsers extends ListRecords
{
    // 
    
    public static function getContextMenu(): ContextMenu
    {
        return ContextMenu::make()
            ->actions([
                Action::make('Create user')
                    ->url(CreateUser::getUrl()),
                ContextMenuDivider::make(),
                Action::make('Trashed user')
                    ->url(TrashedUsers::getUrl()),
            ]);
    }
    
    // 
}
```

### Create Action
You can use ```Filament\Actions\CreateAction```

```php
use Filament\Resources\Pages\ListRecords;
use AymanAlhattami\FilamentContextMenu\ContextMenu;

class ListUsers extends ListRecords
{
    // 
    
    public static function getContextMenu(): ContextMenu
    {
        return ContextMenu::make()
            ->actions([
                \Filament\Actions\CreateAction::make()
            ]);
    }
    
    // 
}
```

### Edit Action
You can use ```Filament\Actions\EditAction```

```php
use Filament\Resources\Pages\ListRecords;
use AymanAlhattami\FilamentContextMenu\ContextMenu;

class ListUsers extends ListRecords
{
    // 
    
    public static function getContextMenu(): ContextMenu
    {
        return ContextMenu::make()
            ->actions([
                \Filament\Actions\EditAction::make()
            ]);
    }
    
    // 
}
```

### View Action
You can use ```Filament\Actions\ViewAction```

```php
use Filament\Resources\Pages\ListRecords;
use AymanAlhattami\FilamentContextMenu\ContextMenu;

class ListUsers extends ListRecords
{
    // 
    
    public static function getContextMenu(): ContextMenu
    {
        return ContextMenu::make()
            ->actions([
                \Filament\Actions\ViewAction::make()
            ]);
    }
    
    // 
}
```

### Delete Action
You can use  ```Filament\Actions\DeleteAction```

```php
use Filament\Resources\Pages\ListRecords;
use AymanAlhattami\FilamentContextMenu\ContextMenu;

class ListUsers extends ListRecords
{
    // 
    
    public static function getContextMenu(): ContextMenu
    {
        return ContextMenu::make()
            ->actions([
                \Filament\Actions\DeleteAction::make()
            ]);
    }
    
    // 
}
```

### Export Action
You can use ```Filament\Actions\ExportAction```

```php
use Filament\Resources\Pages\ListRecords;
use AymanAlhattami\FilamentContextMenu\ContextMenu;

class ListUsers extends ListRecords
{
    // 
    
    public static function getContextMenu(): ContextMenu
    {
        return ContextMenu::make()
            ->actions([
                \Filament\Actions\ExportAction::make()
            ]);
    }
    
    // 
}
```

### Force Delete Action
You can use ```Filament\Actions\ForceDeleteAction```

```php
use Filament\Resources\Pages\ListRecords;
use AymanAlhattami\FilamentContextMenu\ContextMenu;

class ListUsers extends ListRecords
{
    // 
    
    public static function getContextMenu(): ContextMenu
    {
        return ContextMenu::make()
            ->actions([
                \Filament\Actions\ForceDeleteAction::make()
            ]);
    }
    
    // 
}
```

### Import Action
You can use ```Filament\Actions\ImportAction```

```php
use Filament\Resources\Pages\ListRecords;
use AymanAlhattami\FilamentContextMenu\ContextMenu;

class ListUsers extends ListRecords
{
    // 
    
    public static function getContextMenu(): ContextMenu
    {
        return ContextMenu::make()
            ->actions([
                \Filament\Actions\ImportAction::make()
            ]);
    }
    
    // 
}
```

### Replicate Action
You can use ```Filament\Actions\ReplicateAction```

```php
use Filament\Resources\Pages\ListRecords;
use AymanAlhattami\FilamentContextMenu\ContextMenu;

class ListUsers extends ListRecords
{
    // 
    
    public static function getContextMenu(): ContextMenu
    {
        return ContextMenu::make()
            ->actions([
                \Filament\Actions\ReplicateAction::make()
            ]);
    }
    
    // 
}
```

### Restore Action
You can use ```Filament\Actions\RestoreAction```

```php
use Filament\Resources\Pages\ListRecords;
use AymanAlhattami\FilamentContextMenu\ContextMenu;

class ListUsers extends ListRecords
{
    // 
    
    public static function getContextMenu(): ContextMenu
    {
        return ContextMenu::make()
            ->actions([
                \Filament\Actions\RestoreAction::make()
            ]);
    }
    
    // 
}
```

### Note 
For action to have a nice look, use ```->link()``` method for the action
 
```php
public static function getContextMenu(): ContextMenu
{
    return ContextMenu::make()
        ->actions([
            Action::make('Create user')
                ->url(CreateUser::getUrl())
                ->link()
            ]);
}
```

## Testing

```bash
composer test
```

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information on what has changed recently.

## Contributing

Please see [CONTRIBUTING](.github/CONTRIBUTING.md) for details.

## Security Vulnerabilities

Please review [our security policy](../../security/policy) on how to report security vulnerabilities.

## Credits

- [aymanalhattami](https://github.com/aymanalhattami)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
