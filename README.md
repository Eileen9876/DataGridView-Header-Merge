# DataGridView 合併表格標頭

![DataGridView-Header-Merge 結果範例](https://github.com/user-attachments/assets/02bcabed-8188-4168-8da6-41f998b25e75)

使用範例
```csharp
// 資料設置
DataTable table = new DataTable("NestedHeadersTable");
table.Columns.Add("ID", typeof(int));
table.Columns.Add("Name", typeof(string));
table.Columns.Add("Age", typeof(int));
table.Columns.Add("Email", typeof(string));
table.Columns.Add("Phone", typeof(string));
table.Columns.Add("Degree", typeof(string));
table.Columns.Add("School", typeof(string));
table.Columns.Add("Graduation Year", typeof(string));
table.Rows.Add(1, "Alice", 30, "alice@example.com", "123-456-7890", "碩士", "A大學", "2012");
table.Rows.Add(2, "Bob", 25, "bob@example.com", "234-567-8901", "碩士", "B大學", "2016");
table.Rows.Add(3, "Charlie", 35, "charlie@example.com", "345-678-9012", "博士", "C大學", "2010");

// 資料顯示順序
List<string> table_col = new List<string> { "ID", "Name", "Age", "Email", "Phone", "Degree", "School", "Graduation Year" };

// 標頭設置
List<KeyValuePair<string, string[]>> header = new List<KeyValuePair<string, string[]>>
{
    new KeyValuePair<string, string[]>("序號", null),
    new KeyValuePair<string, string[]>("個人資訊", new string[] { "姓名", "年齡" }),
    new KeyValuePair<string, string[]>("聯繫資訊", new string[] { "電子郵件", "電話" }),
    new KeyValuePair<string, string[]>("教育背景", new string[] { "學歷", "學校", "畢業年份" })
};

// 標頭處理
MyLib.DataGridView_Operator op = new MyLib.DataGridView_Operator(dataGridView1);
op.Set_Data(header, table, table_col);
```
