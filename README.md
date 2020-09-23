<div align="center">

## Cookie Basics


</div>

### Description

The first time the users comes to the page, it'll have a text box and a button. Once you type in your nick and hit Set Nick, it'll display Welcome [the nick they entered]. This is just an example on how-to set/read cookies.
 
### More Info
 
The code asks you to enter a nick/name.

This example is to provide newusers info on how-to use cookies.

request.cookies("Var") - Get's a variable

response.cookies("Var") = "blah" - Set's a varible

"" is like the C command null

Once your nick/name is set, every time you goto the page, it'll Say Welcome [Nick]

None Known


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Markus D](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/markus-d.md)
**Level**          |Beginner
**User Rating**    |5.0 (35 globes from 7 users)
**Compatibility**  |ASP \(Active Server Pages\)
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__4-1.md)
**World**          |[ASP / VbScript](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/asp-vbscript.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/markus-d-cookie-basics__4-6109/archive/master.zip)

### API Declarations

This code was porduced by Fluid of Fluid Enterprises [http://fluid.hack3r.com]. If may be freely distributed but it would be nice if you contacted me and told that your using it.


### Source Code

```
' Put this at the top of the page
<%
If (request("REQUEST_METHOD") = "POST") then
Dim Nick
nick = request("Nick")
response.cookies("Nick") = nick
end if
%>
'Put this where you want the Welcome Nick
<%
if request.cookies("Nick") <> "" then
response.write "Welcome "
response.write request.cookies("Nick")
end if
%>
'Put this where you want the text box to appear
<%
if request.cookies("Nick") = "" then
response.write "<BR><FORM NAME='message' METHOD='POST' ACTION='THIS_FILES_NAME.asp'><INPUT TYPE='text' NAME='Nick' Size='10' MAXLENGTH='25'>&nbsp;&nbsp;&nbsp;<INPUT TYPE='SUBMIT' VALUE='Set Nick'>"
end if
%>
```

