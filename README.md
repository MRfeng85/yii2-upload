Yii2 插件整合-图片上传（file-upload）

实例教程：稍后附上

安装扩展：

1.composer require mrfeng/file_upload


2.在使用图片上传控件的控制器（controller）中，加入以下代码

    public function actions()
    {
        return [
            'upload' => [
                'class' => 'mrfeng\yii2upfile\UploadAction',
                'config'=>[
                    //配置图片上传存储绝对地址
                    'uploadFilePath'=>dirname(dirname(__DIR__)).'/uploads',
                    //配置图片上传格式化地址
                    'imagePathFormat'=>'/image/{yyyy}{mm}{dd}/{time}{rand:6}'
                ]
            ]
        ];
    }
    
3.views渲染图片上传界面有两种方式：

<pre>
    //'config'=>['domain_url'=>'http://pic.yygo.com'] 配置图片访问前缀 我这里是专门为上传目录绑定一个二级域名
    <?= $form->field($model,'thumb')->widget('mrfeng\yii2upfile\FileUpload',['config'=>['domain_url'=>'http://pic.yygo.com']]);?>

</pre>

