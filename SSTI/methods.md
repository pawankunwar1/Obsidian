-> Twig for PHP , Freemarker for Java, ERB for Ruby , Jinja for Python.
--> Basic payloads -> ``{{7*7}}``, `${7*7}`, `${{7*7}}`, `<%= 7*7 %>`, `#{7*7}`

<mark style="background: #FF5582A6;">Step 1:-</mark>
FUzz the payload ``${{<%[%'"}}@{%\.#{<%=`` in every input fields and see how server responses. If an error message is returned in the server responses, this indicates that the application is potentially vulnerable.
Analysing the error message could help determine which template engine is being used.

<mark style="background: #FF5582A6;">Step 2:-</mark>
if we go to page like `http://domain.com/sometinghere` and if page reflect `http://domain.com/somethinghere` not found then we can try to inject SSTI payload in `/somethinghere`.



