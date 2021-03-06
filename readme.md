## Codeigniter 3.1.0 Integrated with Illuminate Database Eloquent

### Requires

php: >=5.3.7

### Installation

Install the Illuminate Database package with Composer:

```sh
$ composer install
```

### Using The Eloquent ORM

**Example:**

Model

```php
<?php
use \Illuminate\Database\Eloquent\Model as Eloquent;

class User extends Eloquent{
    protected $table = 'users';

}
```

Controller

```php
defined('BASEPATH') OR exit('No direct script access allowed');

class Home extends CI_Controller {

	public function index()
	{
		$this->load->model('user');
		$users = User::where('votes', '>', 1)->get();
		$this->load->view('home/index', ['users' => $users]);
	}
}
```
### Bonus
dd() Function is also implemented;
Example:
```php
class Home extends CI_Controller {

	public function index()
	{
		$this->load->model('user');
		$users = User::all();
        dd($users);
	}
}
```

### Documentation

- [CodeIgniter documentation](http://www.codeigniter.com/user_guide/)

- [Laravel framework - Eloquent documentation](https://laravel.com/docs/9.x/eloquent)


### Inspired From

- [codeigniter-eloquent](https://github.com/aduartem/codeigniter-eloquent/)

