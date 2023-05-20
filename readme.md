# huggingface 的上传文件流程 
    python -m pip install huggingface_hub
    # 登录 使用token
    huggingface-cli login
如果之前登录过了，直接运行这个代码就能登录成功。

    huggingface-cli whoami
    # 输入token 请注意是read还是write


安装git-lfs

    git lfs install

如果文件大于5GB，需要执行下面的代码

    huggingface-cli lfs-enable-largefiles .

将创建好的仓库，clone到本地
    
    git clone https://huggingface.co/<your-username>/<your-model-name>
    cd <your-model-name>
    git lfs install
    git lfs track * # 追踪所有要上传的大文件
    git add .gitattributes # 添加先上传的属性文件
    git  commit -m "Add attributes"  # 添加属性文件上传的说明
    git push  # 上传属性文件
    git add * # 添加要上传的大文件，*表示路径下的所有文件
    git commit -m "git LFS commit" # 添加大文件上传的说明
    git push  # 上传文件
    

    # 测试"# huggingface" 
