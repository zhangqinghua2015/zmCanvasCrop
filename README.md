# zmCanvasCrop
canvas实现前端完全剪裁图片并上传base64码

## 优势
  传统图片上传剪裁:
    前端需要把图片先上传到后端 -> 后端成功获取后、反馈 -> 前端开始裁剪，裁剪后获取的坐标、宽高等参数传入后端
     -> 后端拿到数据进行裁剪 -> 返回成功数据给前端

  当前方式:
    前端把图片载入到canvas画布，前端页面进行裁剪，裁剪的区域转化为base64编码 -> ajax传给后端、后端根据base64生成图片、保存

  1. 可以减少前后端交互次数
  1. 功能耦合性小
  1. 减少交互次数之后，速度更快
  1. 可维护性强
  
  java后台代码示例:  
  base64 = base64.substring(base64.indexOf("base64,")+"base64,".length());  
  //用的spring的工具类  
  byte[] bytes = Base64Utils.decodeFromString(base64);  
  //将bytes写入文件，用的apache工具类  
  FileUtils.writeByteArrayToFile(targetFile, bytes);  

# 当前仍然是demo状态，代码有待后续做更好的封装
