# Laravel check for constraint violation

https://stackoverflow.com/questions/26363271/laravel-check-for-constraint-violation

> You are looking for the 23000 Error code (Integrity Constraint Violation). If you take a look at QueryException class, it extends from PDOException, so you can access to `$errorInfo` variable.
> To catch this error, you may try:

```
try {
  // ...
} catch (\Illuminate\Database\QueryException $e) {
    var_dump($e->errorInfo);
}
```

Example output from MySQL
```
array (size=3)
   0 => string '23000' (length=5)
   1 => int 1452
   2 => string 'Cannot add or update a child row: a foreign key constraint fails (...)'
```