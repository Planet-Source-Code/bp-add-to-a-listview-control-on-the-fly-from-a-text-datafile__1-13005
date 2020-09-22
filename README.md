<div align="center">

## Add to a ListView control on the fly from a text datafile


</div>

### Description

This code will read in a two column data file (with the column titles in the first line) and update a listview control quickly and easily. It's easy to add more columns as needed. To use this code, you simply call the function like.

Call load_list_view_two(mylist, "c:\test.dat")
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[BP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/bp.md)
**Level**          |Intermediate
**User Rating**    |4.7 (14 globes from 3 users)
**Compatibility**  |VB 5\.0, VB 6\.0
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__1-1.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/bp-add-to-a-listview-control-on-the-fly-from-a-text-datafile__1-13005/archive/master.zip)





### Source Code

```
Public Sub load_list_box_two(MyList As ListView, MyFile As String)
MyList.ListItems.Clear
MyList.View = lvwReport
Open MyFile For Input As #1
  Input #1, one$, two$
  X = MyList.ColumnHeaders.Add(, , one$)
  X = MyList.ColumnHeaders.Add(, , two$)
  Do Until EOF(1)
    Input #1, one$, two$
    X = MyList.ListItems.Add(, , one$).ListSubItems.Add(, , two$)
  Loop
Close #1
End Sub
```

