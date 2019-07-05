一、添加时间戳
1.修改noteslist_item.xml中的样式，增加要显示时间戳的TextView:

https://github.com/ImmortalSchoolmaster/NotePad-master/blob/master/1.png

2.进入NotesList.java PROJECTION 契约类的变量值加一列:

https://github.com/ImmortalSchoolmaster/NotePad-master/blob/master/2.png

3.修改SimpleCursorAdapter的dataColumns和viewIDs的相关值:

https://github.com/ImmortalSchoolmaster/NotePad-master/blob/master/3.png

https://github.com/ImmortalSchoolmaster/NotePad-master/blob/master/4.png

4.发现这样显示的时间戳格式不对，因此要把时间戳改为以时间格式存入，改动地方分别为NotePadProvider中的insert方法和NoteEditor中的updateNote方法。前者为创建笔记时产生的时间，后者为修改笔记时产生的时间:

https://github.com/ImmortalSchoolmaster/NotePad-master/blob/master/5.png

标题下方出现时间：

https://github.com/ImmortalSchoolmaster/NotePad-master/blob/master/6.png

二、笔记查询

1.找到菜单的list_options_menu.xml文件，添加一个搜索的item:

https://github.com/ImmortalSchoolmaster/NotePad-master/blob/master/7.png

2.在NotesList中找到onOptionsItemSelected方法，在switch中添加搜索的case语句:

https://github.com/ImmortalSchoolmaster/NotePad-master/blob/master/8.png

3.新建一个名为NoteSearch的activity用来显示跳转的搜索界面的内容和功能。在安卓中有个用于搜索控件：SearchView，可以把SearchView跟ListView相结合，动态地显示搜索结果。

NoteSearch.java文件的布局文件note_search_list.xml:

https://github.com/ImmortalSchoolmaster/NotePad-master/blob/master/9.png

NoteSearch.java:

https://github.com/ImmortalSchoolmaster/NotePad-master/blob/master/10.png

4.最后要在AndroidManifest.xml注册NoteSearch：

https://github.com/ImmortalSchoolmaster/NotePad-master/blob/master/11.png

搜索栏可根据标题查询：

https://github.com/ImmortalSchoolmaster/NotePad-master/blob/master/12.png

https://github.com/ImmortalSchoolmaster/NotePad-master/blob/master/13.png

https://github.com/ImmortalSchoolmaster/NotePad-master/blob/master/14.png


