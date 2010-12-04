@complexity

O(start+n) (with start being the start index and n the total
length of the requested range). Note that the lookup part of this command is
O(1) so for small strings this is actually an O(1) command.

Return a subset of the string from offset _start_ to offset _end_
(both offsets are inclusive).
Negative offsets can be used in order to provide an offset starting from
the end of the string. So -1 means the last char, -2 the penultimate and
so forth.

The function handles out of range requests without raising an error, bu
just limiting the resulting range to the actual length of the string.

@return

@bulk-reply

@examples

    SET s This is a string
    OK
    SUBSTR s 0 3
    This
    SUBSTR s -3 -1
    ing
    SUBSTR s 0 -1
    This is a string
    SUBSTR s 9 100000
     string