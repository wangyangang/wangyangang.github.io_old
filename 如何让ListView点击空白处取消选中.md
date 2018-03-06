当ListView选择一条数据的之后，再点击ListViewItem之外的地方或者ListView之外的地方，发现ListView还是保持原来的记录处于选中的状态。想实现点击空白让ListView取消选中，实现方法如下：

```csharp

private void lvwSJWJ_MouseUp(object sender, MouseEventArgs e)
{
  if(e.Button== MouseButtons.Left)
  {
    if (lvwSJWJ.SelectedItems.Count &amp;amp;lt;= 0)
    {
      selectedAttachments.Clear();
    }
  }
}

```

其中，selectedAttachments是我的接收ListView选择项的变量，当鼠标抬起，并且ListView选择项为零的时候，清空该变量。

另外在ListView控件以外的窗口单击的时候，可以添加以下代码：

```csharp

if (lvwSJWJ.SelectedItems.Count>0)
  lvwSJWJ.SelectedItems.Clear();
if (lvwSJWJ.FocusedItem != null)
  lvwSJWJ.FocusedItem = null;
selectedAttachments.Clear();

```
参见：

<a href="http://blog.csdn.net/shiwei0124/article/details/5291157">C# listview之点击空白区仍然不失去选中项的状态</a>

<a href="http://raocuncun.blog.163.com/blog/static/161666790201110411187828/">解决listview控件点击空白区仍然不失去选中项的状态 </a>
