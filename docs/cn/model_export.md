[English](../en/model_export.md) | 简体中文

# 模型导出

## 使用 `trtyolo` CLI 导出模型

`tensorrt_yolo` 提供了一个便捷的命令行界面（CLI）工具 `trtyolo`，用于将 ONNX 模型导出为适用于项目推理的格式，并集成了 TensorRT 插件。您可以通过运行 `trtyolo export --help` 查看详细的导出命令帮助信息。

> [!NOTE]  
> 在导出 PP-YOLOE 和 PP-YOLOE+ 的 ONNX 模型时，仅会调整 batch 维度，而 height 和 width 维度保持不变。您需要在 [PaddleDetection](https://github.com/PaddlePaddle/PaddleDetection) 中进行相关设置，默认值通常为 640。
>
> 官方仓库如 [YOLOv6](https://github.com/meituan/YOLOv6/tree/main/deploy/ONNX#tensorrt-backend-tensorrt-version-800)、[YOLOv7](https://github.com/WongKinYiu/yolov7#export)、[YOLOv9](https://github.com/WongKinYiu/yolov9/issues/130#issue-2162045461) 已经提供了带有 EfficientNMS 插件的 ONNX 模型导出功能，因此此处不再重复提供。

### 导出命令示例

```bash
# 导出远程仓库中的 YOLOv3 模型
trtyolo export -w yolov3.pt -v yolov3 -o output

# 导出本地仓库中的 YOLOv5 模型
trtyolo export -w yolov5s.pt -v yolov5 -o output --repo_dir your_local_yolovs_repository

# 使用 Ultralytics 训练的 YOLO 系列模型（YOLOv3、YOLOv5、YOLOv6、YOLOv8、YOLOv9、YOLOv10、YOLO11），并指定插件参数，以动态 batch 导出
trtyolo export -w yolov8s.pt -v ultralytics -o output --max_boxes 100 --iou_thres 0.45 --conf_thres 0.25 -b -1

# 导出 YOLOv10 模型，高度 1080，宽度 1920
trtyolo export -w yolov10s.pt -v yolov10 -o output --imgsz 1080 1920

# 导出 YOLO11 OBB 模型
trtyolo export -w yolo11n-obb.pt -v yolo11 -o output

# 导出 PP-YOLOE 和 PP-YOLOE+ 模型
trtyolo export --model_dir modeldir --model_filename model.pdmodel --params_filename model.pdiparams -o output
```

## 使用 `trtexec` 构建 TensorRT 引擎

导出的 ONNX 模型可以通过 `trtexec` 工具构建为 TensorRT 引擎。

```bash
# 静态 batch
trtexec --onnx=model.onnx --saveEngine=model.engine --fp16

# 动态 batch
trtexec --onnx=model.onnx --saveEngine=model.engine --minShapes=images:1x3x640x640 --optShapes=images:4x3x640x640 --maxShapes=images:8x3x640x640 --fp16

# YOLOv8-OBB 静态 batch
trtexec --onnx=yolov8n-obb.onnx --saveEngine=yolov8n-obb.engine --fp16 --staticPlugins=./lib/plugin/libcustom_plugins.so --setPluginsToSerialize=./lib/plugin/libcustom_plugins.so

# YOLO11-OBB 动态 batch
trtexec --onnx=yolo11n-obb.onnx --saveEngine=yolo11n-obb.engine --fp16 --minShapes=images:1x3x640x640 --optShapes=images:4x3x640x640 --maxShapes=images:8x3x640x640 --staticPlugins=./lib/plugin/libcustom_plugins.so --setPluginsToSerialize=./lib/plugin/libcustom_plugins.so
```

> [!NOTE]  
> 在使用 `--staticPlugins` 和 `--setPluginsToSerialize` 参数构建包含自定义插件的动态模型时，如果遇到错误 `[E] Error[4]: IRuntime::deserializeCudaEngine: Error Code 4: API Usage Error (Cannot register the library as plugin creator of EfficientRotatedNMS_TRT exists already.)`，这通常意味着引擎构建已成功，但在加载并反序列化引擎时检测到插件重复注册。这种情况下，可以忽略该错误。
