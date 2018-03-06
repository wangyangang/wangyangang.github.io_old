现在并没有详细弄懂这玩意是啥意思，反正在gridControl里用的时候有几点实践：

DRAGDROP里用需要PORINTTOSCREEN处理：

```csharp

GridHitInfo hitInfo1;
private void gridControl1_DragDrop(object sender, DragEventArgs e)
{
    List<DataRow> dragData = e.Data.GetData(typeof(List<DataRow>)) as     List<DataRow>;
    if (dragData == null || dragData.Count < 1)
    return;

    Point targetPt = PointToScreen(gridControl1.Location);

    hitInfo1 = gridView1.CalcHitInfo(new Point(e.X - targetPt.X, e.Y - targetPt.Y));

    //hitInfo1 = gridView1.CalcHitInfo(new Point(e.X, e.Y));
    if (hitInfo1 == null || hitInfo1.RowHandle < 0)
      return;
      
```

MOUSEDOWN里不需做处理：

```csharp

private void gridControl2_MouseDown(object sender, MouseEventArgs e)
{
    hitInfo2 = gridView2.CalcHitInfo(new Point(e.X, e.Y));
}

```
