# #size, #count or #length?

## Length

Loads all objects to count them, see:

```sql
select * from users
```

This means we may be performing unnecessary queries, so not recommended.

## Count

Count is equivalent to:

```sql
select count(*) from users
```

Here, all users are not loaded just to count them. This is better for performance.

## Size

Size chooses between 1.) checking if we have already loaded the assoc -> then it will just call transform to an array and count the elements that way and 2.) the counter cache -> if you have a field named user_count in your website (as an example) model then size will return this field instead. Failing that, it will return #count.

## TLDR

Size is usually more performant and the better to use option.