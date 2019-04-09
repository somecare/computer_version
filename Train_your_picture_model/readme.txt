# 比较简单方式的一种方式，使用Google提供的接口，继续使用已经训练好的Inception模型继续训练。
# 


# 运行方式：
  
  运行批处理文件 retrain.bat（windows下，其它系统依据此格式修改），注意参数 
  运行完成后,用Validation_trained_model.ipynb验证模型


  
# 文件说明 



data    文件夹                  # 图像数据，animal，flower，guitar等，一个文件夹代表一个类别数据
bottleneck 文件夹               # 可以理解为利用inception模型提取图片的特征，放在该文件夹下
images  文件夹                  # 验证数据
inception_model 文件夹          # 模型存放位置
output_labels.txt		# 标签内容
retrain.bat                     # 脚本文件
retrain.py			# Google提供接口


# 注意点：

1. data文件夹下有几个分类就是有几个输出。
2. 该程序将inception模型最后的全链接和softmax分类层去掉，重新训练FC层。前面的卷积层没有参与训练。
3. 整个过程中，相当于只训练全连接层，输入为提取到的特征。
4. 属于简单的迁移学习
5. 这里的数据是特殊准备的，图像之间的差异很明显，若图像相似度很高，此种方式不推荐。
6. 模型参数请自行查看retrain.py








