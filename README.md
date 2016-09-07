该项目是基于：[ZXingLib](https://github.com/xuyisheng/ZXingLib) 进行修改的，更改了扫描界面，添加了类`RGBLuminanceSource(scanBitmap)`,可以进行从图片中识别条形码/二维码；具体使用请参见我的博客：http://blog.csdn.net/txadf/article/details/52152924 <br>


扫描识别二维码：
```
Intent intent = new Intent(MainActivity.this,CaptureActivity.class);
startActivityForResult(intent, 0);
```
在`onActivityResult`中处理返回结果：
```
@Override
  protected void onActivityResult(int requestCode, int resultCode, Intent data) {
      super.onActivityResult(requestCode, resultCode, data);
      if(requestCode == 0)
      {
        if (resultCode == RESULT_OK) {
            Bundle bundle = data.getExtras();
            String result = bundle.getString("result");
            ToastUtils.showToast(MainActivity.this,result);
        }
      }
  }
```
