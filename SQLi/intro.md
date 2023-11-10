-> SQL Injection mainly have 3 types:-
1) IN-BAND
2) Out-of-Band
3) Inferential or Blind

1) In-Band -> In-Band Sql Injection, attackers can launch the attack and obtain through the same communication channel. In-Band techniques are a) ERROR-BASED IN-BAND b) UNION-BASED INJECTIONS
 a) ERROR-BASED Injections:- Get information about database, its structure , and its data from error messages. eg giving `'` or `"` in search field or other input field and it gives error.
 b) UNION-BASED injections:- Combine the results from a legitimate query with those from our attack to extract data.

2) OUT-OF-BAND -> Exfiltrate Data using different channel than the request was made with -> can use HTTP, DNS -> Make an HTTP connection to send results to a different web server.
3) INFERENTIAL or BLIND INJECTIONS :- Used when data doesn't GET back to the attacker -> Often use TIMED DELAYS or BOOLEAN CONDITIONS.


--> DETERMINING THE NUMBER OF COLUMNS REQUIRED IN A SQL INJECTION UNION ATTACK
    -> When performing a SQL injection UNION attack, there are two effective methods to determine how many columns are being returned from the original query.
    1) The first method involves injecting a series of `ORDER BY` clauses and incrementing the specified column index until an error occurs. For example, assuming the injection point is a quoted string within the `where` clause of the original query, you would submit:
      `'+ORDER+BY+1--`
      `'+ORDER+BY+2--`
      `'+ORDER+BY+3--`
      etc
            This series of payloads modifies the original query to order the results by different columns in the result set. The column in an `ORDER BY` clause can be specified by its index, so we dont need to know the names of any columns.  When the specified column index exceeds the number of actual columns in the result set, the database returns an error such as `The Order BY position number 3 is out of range of the number of items in the select list.`
            The application  might actually returns the database error in its HTTP response, or it might return a generic error, or simply return no results. Provided you can detect some difference in the application's response, you can infer how many columns are being returned from the query.
    2) The second method involves submitting a series of `UNION SELECT` payloads specifying a different number of null values:
          `' UNION SELECT NULL--`
          ` UNION SELECT NULL,NULL--`
          `UNION SELECT NULL,NULL,NULL--`
          etc
          If the number of nulls does not match the number of columns, the database returns an error, such as `ALL queries combined using a UNION, INTERSECT or EXCEPT operator must have an equal number of expressions in thier target lists`
          Again the application might actually return this error message, or might just return a generic error or results. When the number of nulls matches the number of columns, the databases returns an additional row in the result set, containing null values in each column. The effect on the resulting HTTP response depends on the applications code.