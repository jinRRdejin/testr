你fork了我的仓库，我在里面没法写，你把所有的东西都写到这个README文件里面


仔细检查是不是文件名错了


String jsonString = sharedPreferences.getString("_default_config_tag", "");
这一句就是取数据的吧， 看看是不是_default_config_tag写错了

你能一次取出share里面的所有数据吗？看看能不能获取其他的数据

你打印出来文件名看看，就算那个fileName

你还要确认里面是不是确实有数据

你是C进程去删数据，A 还是 B去写数据 还是C?

再看一下你的模式是不是错了

对于跨应用使用sharedPreferences，使用模式Context.MODE_PRIVATE,这样就不能被其他程序访问到
  Activity.MODE_PRIVATE：默认操作模式，代表该文件是私有数据，只能被应用本身访问，在该模式下，写入的内容会覆盖原文件的内容，如果想把新写入的内容追加到原文件中，可以使用Activity.MODE_APPEND  
  Activity.MODE_WORLD_READABLE：表示当前文件可以被其他应用读取，  
  Activity.MODE_WORLD_WRITEABLE：表示当前文件可以被其他应用写入；  
  如果希望文件被其他应用读和写，可以传入:Activity.MODE_WORLD_READABLE+Activity.MODE_WORLD_WRITEABLE  
  Activity.MODE_APPEND：该模式会检查文件是否存在，存在就往文件追加内容，否则就创建新文件

