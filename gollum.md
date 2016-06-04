### Diagrams
Diagrams using websequencediagrams.com
```
{{{{{{ blue-modern
User->+A: DoWork
A->*+B: <<createRequest>>
B->*+C: DoWork
C-->B: WorkDone
destroy C
B-->-A: RequestCreated
A->User: Done
}}}}}}
```


You can syntax highlight a file from your repository. Naturally, when the file is updated and the page refreshed in browser, the 
code snippet is updated as well:

```ruby:/lib/gollum/app.rb```

In this case, the /lib/gollum/app.rb file will be included in the page, and syntax highlighted.

