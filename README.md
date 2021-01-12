# postgres-tips

# check the process when something is in stuck
```
SELECT pid, relname FROM pg_locks l JOIN pg_class t ON l.relation = t.oid AND t.relkind = 'r' WHERE t.relname = '[table name]'
```

this will show the process id.

# kill the process
```
SELECT pg_terminate_backend([pid]);
```
make sure to put the process id from the above query
