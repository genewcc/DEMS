# DEMS

2022.04.27 修改為特定日期中，可以依據時間產出報表

直接在reportpdf及repotccsv的查詢 sql server字串部分修改:

string sh1 = a.ToString("yyyy-MM-dd HH:mm:ss");   // 增加時間的部分
string sh2 = b.ToString("yyyy-MM-dd HH:mm:ss");
SqlDataAdapter sqld = new SqlDataAdapter("Select * FROM [Table] where 消磁時間>=@Date1 and 消磁時間<=@Date2", conn);   // 查詢日期及時間的部分
sqld.SelectCommand.Parameters.Add(new SqlParameter("@Date1", sh1));
sqld.SelectCommand.Parameters.Add(new SqlParameter("@Date2", sh2));

參考網站:
https://stackoverflow.com/questions/17418258/datetime-format-to-sql-format-using-c-sharp
https://stackoverflow.com/questions/2191120/net-datetime-to-sqldatetime-conversion
https://www.w3schools.com/sql/func_sqlserver_convert.asp
https://www.796t.com/content/1507465327.html
https://ithelp.ithome.com.tw/articles/10226348
https://www.fooish.com/sql/date.html
