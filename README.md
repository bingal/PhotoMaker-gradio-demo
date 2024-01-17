# About
为了顺利在本地运行 PhotoMaker gradio demo，做了点微小调整
官方提供了两个 space 可供体验：
* [PhotoMaker](https://huggingface.co/spaces/TencentARC/PhotoMaker)
* [PhotoMaker-Style](https://huggingface.co/spaces/TencentARC/PhotoMaker-Style)

## 主要调整
* 模型加载方式由 from_pretrained 改成了 from_single_file，这样方便网络顺畅的地方手动下载模型，并指定模型路径。
* 调整了启动方式 `demo.launch(server_name="0.0.0.0", server_port=7860)` 可供其他机器访问，如果只是本机访问可调整成 `demo.launch()`

## PhotoMaker demo 涉及的模型
* [RealVisXL_V3.0.safetensors](https://huggingface.co/SG161222/RealVisXL_V3.0/tree/main)
* [photomaker-v1.bin](https://huggingface.co/TencentARC/PhotoMaker/tree/main)


## PhotoMaker-Style demo 涉及的模型
* [sdxlUnstableDiffusers_v11.safetensors](https://civitai.com/models/84040/sdxl-unstable-diffusers-yamermix)
* [xl_more_art-full.safetensors](https://civitai.com/models/124347/
* [photomaker-v1.bin](https://huggingface.co/TencentARC/PhotoMaker/tree/main)xlmoreart-full-xlreal-enhancer)
注意：`xl_more_art-full.safetensors` 模型默认下载文件名是 `xl_more_art-full-v1.safetensors` ，要改成 `xl_more_art-full.safetensors`

## 使用方法
先安装 `PhotoMaker` 依赖
1. `git clone https://github.com/TencentARC/PhotoMaker.git`
2. `cd PhotoMaker`
3. `pip install -r requirements.txt`

拉取本项目
1. `git clone https://github.com/bingal/PhotoMaker-gradio-demo.git`
2. 下载模型文件到本地
3. 修改 `gradio_demo/app.py` 和 `style_gradio_demo/app.py` 中的模型路径
4. 运行 `python gradio_demo/app.py` 或 `python style_gradio_demo/app.py`
5. 在浏览器中打开 `http://127.0.0.1:7860/` 即可访问