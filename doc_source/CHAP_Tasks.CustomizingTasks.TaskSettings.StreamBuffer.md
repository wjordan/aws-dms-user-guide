# Stream Buffer Task Settings<a name="CHAP_Tasks.CustomizingTasks.TaskSettings.StreamBuffer"></a>

You can set stream buffer settings using the AWS CLI, include the following:

+ `StreamBufferCount` – Use this option to specify the number of data stream buffers for the migration task\. The default stream buffer number is 3\. Increasing the value of this setting may increase the speed of data extraction\. However, this performance increase is highly dependent on the migration environment, including the source system and instance class of the replication server\. The default is sufficient for most situations\.

+ `StreamBufferSizeInMB` – Use this option to indicate the maximum size of each data stream buffer\. The default size is 8 MB\. You might need to increase the value for this option when you work with very large LOBs or if you receive a message in the log files stating that the stream buffer size is insufficient\. When calculating the size of this option you can use the following equation: \[Max LOB size \(or LOB chunk size\)\]\*\[number of LOB columns\]\*\[number of stream buffers\]\*\[number of tables loading in parallel per task\(MaxFullLoadSubTasks\)\]\*3

+ `CtrlStreamBufferSizeInMB` – Use this option to set the size of the control stream buffer\. Value is in MB, and can be from 1 to 8\. The default value is 5\. You may need to increase this when working with a very large number of tables, such as tens of thousands of tables\.