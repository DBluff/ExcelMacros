# ExcelMacros

Mass Find / Replace using key values
Alt-F11 to open VBA in excel
F5 to run the script


Sub MultiFindNReplace()
'Update 20140722
Dim Rng As Range
Dim InputRng As Range, ReplaceRng As Range
xTitleId = "Dougs Mass Replace"
Set InputRng = Application.Selection
Set InputRng = Application.InputBox("Original Range ", xTitleId, InputRng.Address, Type:=8)
Set ReplaceRng = Application.InputBox("Replace Range :", xTitleId, Type:=8)
Application.ScreenUpdating = False
For Each Rng In ReplaceRng.Columns(1).Cells
    InputRng.Replace what:=Rng.Value, replacement:=Rng.Offset(0, 1).Value, MatchCase:=True
Next
Application.ScreenUpdating = True
End Sub
