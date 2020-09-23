<div align="center">

## Check if your MDI Child form is already loaded


</div>

### Description

Checks for other instances of your form on your Parent MDI form. If one is found, load that one. Else, Load a new one!

The other example is too long and requires a lot of work, while this one is easy doesnt require you to catch an error.

This is my own work, and i'll share it to all ot you!
 
### More Info
 
ShowForm(new <form>)

<form> -> the Name of your form

fMain -> the Name of your MDI Form


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[rhai](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/rhai.md)
**Level**          |Beginner
**User Rating**    |4.8 (24 globes from 5 users)
**Compatibility**  |VB\.NET
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__10-1.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/rhai-check-if-your-mdi-child-form-is-already-loaded__10-4007/archive/master.zip)





### Source Code

```
	Private Sub ShowForm(ByVal fForm As Form)
		Dim objForms As Form
		For Each objForms In fMain.MdiChildren
			If objForms.Name = fForm.Name Then
				fForm.Dispose()
				fForm = Nothing
				objForms.Show()
				objForms.Visible = True
				objForms.Focus()
				Return
			End If
		Next
		With fForm
			.MdiParent = fMain
			.Show()
		End With
	End Sub
```

