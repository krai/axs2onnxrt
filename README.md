# axs2onnxrt

Recipe for downloading the Onnxruntime SDK, libraries and models.

Download and extract the onnxrt library.
```
axs byquery extracted,onnxruntime_lib
```

Download the pre-generated onnxrt resnet50 model.
```
axs byquery onnx_model,converted,model_name=resnet50
```

If you want to generate the model yourself use this command with the base resnet50 model:
```
python -m tf2onnx.convert --graphdef resnet50_v1.pb --output resnet50_v1_modified.onnx --inputs input_tensor:0[-1,224,224,3] --inputs-as-nchw input_tensor:0[-1,224,224,3] --outputs ArgMax:0
```
