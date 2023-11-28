# Creating and dropping a table during Laravel test

https://stackoverflow.com/questions/50819257/creating-and-dropping-a-table-during-laravel-test

```
private function createStubTable()
{
    Schema::create('stubs', function ($table) {
    $table->temporary();
        $table->increments('id');
        $table->string('name');
        $table->timestamps();
    });
}
```