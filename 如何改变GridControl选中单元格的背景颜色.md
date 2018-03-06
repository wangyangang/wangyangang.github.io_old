在CustomDrawCell事件里做处理：

```cshap

private void gridView1_CustomDrawCell(object sender, DevExpress.XtraGrid.Views.Base.RowCellCustomDrawEventArgs e)
{
    GridRowCellState state = ((GridCellInfo)e.Cell).State;
    if ((state & GridRowCellState.Selected) == GridRowCellState.Selected)
    {
        e.Appearance.BackColor = Color.Red;
    }
}

```
