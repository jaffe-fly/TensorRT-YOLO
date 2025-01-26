[English](README.en.md) | 简体中文

<div align="center">
  <p>
      <img width="100%" src="assets/logo.png"></a>
  </p>
</div>

## <div align="center">🚀 TensorRT YOLO</div>

<p align="center">
    <a href="./LICENSE"><img alt="GitHub License" src="https://img.shields.io/github/license/laugh12321/TensorRT-YOLO?style=for-the-badge"></a>
    <a href="https://github.com/laugh12321/TensorRT-YOLO/releases"><img alt="GitHub Release" src="https://img.shields.io/github/v/release/laugh12321/TensorRT-YOLO?style=for-the-badge"></a>
    <a href="https://github.com/laugh12321/TensorRT-YOLO/commits"><img alt="GitHub commit activity" src="https://img.shields.io/github/commit-activity/m/laugh12321/TensorRT-YOLO?style=for-the-badge&color=rgb(47%2C154%2C231)"></a>
    <img alt="GitHub Repo stars" src="https://img.shields.io/github/stars/laugh12321/TensorRT-YOLO?style=for-the-badge&color=%2350e472">
    <img alt="GitHub forks" src="https://img.shields.io/github/forks/laugh12321/TensorRT-YOLO?style=for-the-badge&color=%2320878f">
</p>

<p align="center">
    <a href="/docs/cn/build_and_install.md"><img src="https://img.shields.io/badge/-安装-0078D4?style=for-the-badge&logo=github&logoColor=white"></a>
    <a href="/examples/"><img src="https://img.shields.io/badge/-使用示例-0078D4?style=for-the-badge&logo=github&logoColor=white"></a>
    <a href="#quick-start"><img src="https://img.shields.io/badge/-快速开始-0078D4?style=for-the-badge&logo=github&logoColor=white"></a>
    <a href=""><img src="https://img.shields.io/badge/-API文档-0078D4?style=for-the-badge&logo=github&logoColor=white"></a>
    <a href="https://github.com/laugh12321/TensorRT-YOLO/releases"><img src="https://img.shields.io/badge/-更新日志-0078D4?style=for-the-badge&logo=github&logoColor=white"></a>
</p>

🚀 TensorRT-YOLO 是一款专为 NVIDIA 设备设计的**易用灵活**、**极致高效**的**YOLO系列**推理部署工具。项目不仅集成了 TensorRT 插件以增强后处理效果，还使用了 CUDA 核函数以及 CUDA 图来加速推理。TensorRT-YOLO 提供了 C++ 和 Python 推理的支持，旨在提供📦**开箱即用**的部署体验。包括 [目标检测](examples/detect/)、[实例分割](examples/segment/)、[图像分类](examples/classify/)、[姿态识别](examples/pose/)、[旋转目标检测](examples/obb/)、[视频分析](examples/VideoPipe)等任务场景，满足开发者**多场景**的部署需求。

<div align="center">

[<img src='assets/obb.png' height="138px" width="190px">](examples/obb/)
[<img src='assets/detect.jpg' height="138px" width="190px">](examples/detect/)
[<img src='assets/segment.jpg' height="138px" width="190px">](examples/segment/)
[<img src='assets/pose.jpg' height="138px" width="190px">](examples/pose/)
[<img src='assets/example.gif' width="770px">](examples/videopipe)

</div>

## <div align="center">✨ 主要特性</div>

### 🎯 多样化的 YOLO 支持
- **全面兼容**：支持 YOLOv3 至 YOLOv11 全系列模型，以及 PP-YOLOE 和 PP-YOLOE+，满足多样化需求。
- **灵活切换**：提供简洁易用的接口，支持不同版本 YOLO 模型的快速切换。
- **多场景应用**：提供丰富的示例代码，涵盖[Detect](examples/detect/)、[Segment](examples/segment/)、[Classify](examples/classify/)、[Pose](examples/pose/)、[OBB](examples/obb/)等多种应用场景。

### 🚀 性能优化
- **CUDA 加速**：通过 CUDA 核函数优化前处理流程，并采用 CUDA 图技术加速推理过程。
- **TensorRT 集成**：深度集成 TensorRT 插件，显著加速后处理，提升整体推理效率。
- **多 Context 推理**：支持多 Context 并行推理，最大化硬件资源利用率。
- **显存管理优化**：适配多架构显存优化策略（如 Jetson 的 Zero Copy 模式），提升显存效率。

### 🛠️ 易用性
- **开箱即用**：提供全面的 C++ 和 Python 推理支持，满足不同开发者需求。
- **CLI 工具**：内置命令行工具，支持快速模型导出与推理，提升开发效率。
- **Docker 支持**：提供 Docker 一键部署方案，简化环境配置与部署流程。
- **无第三方依赖**：全部功能使用标准库实现，无需额外依赖，简化部署流程。
- **部署便捷**：提供动态库编译支持，方便调用和部署。

### 🌐 兼容性
- **多平台支持**：全面兼容 Windows、Linux、ARM、x86 等多种操作系统与硬件平台。
- **TensorRT 兼容**：完美适配 TensorRT 10.x 版本，确保与最新技术生态无缝衔接。

### 🔧 灵活配置
- **预处理参数自定义**：支持多种预处理参数灵活配置，包括 **通道交换 (SwapRB)**、**归一化参数**、**边界值填充**。

## <div align="center">🔮 文档教程</div>

- **安装指南**
    - [📦 快速编译安装](docs/cn/build_and_install.md)
- **使用示例**
    - [目标检测 示例](examples/detect/README.md)
    - [实例分割 示例](examples/segment/README.md)
    - [图像分类 示例](examples/classify/README.md)
    - [姿态识别 示例](examples/pose/README.md)
    - [旋转目标检测 示例](examples/obb/README.md)
    - [📹视频分析 示例](examples/VideoPipe/README.md)
    - [多线程多进程 示例](examples/mutli_thread/README.md)
- **API文档**
    - Python API文档（⚠️ 未实现）
    - C++ API文档（⚠️ 未实现）
- **常见问题**
    - ⚠️ 收集中 ...
- **模型支持列表**
    - [🖥️ 模型支持列表](#support-models)

## <div align="center">💨 快速开始</div><div id="quick-start"></div>

### 1. 前置依赖

- **CUDA**：推荐版本 ≥ 11.0.1
- **TensorRT**：推荐版本 ≥ 8.6.1
- **操作系统**：Linux (x86_64 或 arm)（推荐）；Windows 亦可支持

### 2. 安装

- 参考 [📦 快速编译安装](docs/cn/build_and_install.md) 文档。

### 3. 模型导出

- 参考 [🔧 模型导出](docs/cn/model_export.md) 文档，导出适用于该项目推理的ONNX模型并构建为TensorRT引擎。

### 4. 推理示例

> [!NOTE]
>
> `ClassifyModel`、`DetectModel`、`OBBModel`、`SegmentModel` 和 `PoseModel` 分别对应于图像分类（Classify）、检测（Detect）、方向边界框（OBB）、分割（Segment）、姿态估计（Pose）和模型。

- 使用 Python 进行推理：

  ```python
  import cv2
  from tensorrt_yolo.infer import InferOption, DetectModel, generate_labels, visualize

  # 配置推理选项
  option = InferOption()
  option.enable_swap_rb()

  # 初始化模型
  model = DetectModel("yolo11n-with-plugin.engine", option)

  # 加载图片
  im = cv2.imread("test_image.jpg")

  # 模型预测
  result = model.predict(im)
  print(f"==> detect result: {result}")

  # 可视化检测结果
  labels = generate_labels("labels.txt")
  vis_im = visualize(im, result, labels)
  cv2.imwrite("vis_image.jpg", vis_im)

  # 克隆模型并进行预测
  clone_model = model.clone()
  clone_result = clone_model.predict(im)
  print(f"==> detect clone result: {clone_result}")
  ```

- 使用 C++ 进行推理：

  ```cpp
  #include <memory>
  #include <opencv2/opencv.hpp>

  // 为了方便调用，模块除使用CUDA、TensorRT外，其余均使用标准库实现
  #include "deploy/model.hpp"  // 包含模型推理相关的类定义
  #include "deploy/option.hpp"  // 包含推理选项的配置类定义
  #include "deploy/result.hpp"  // 包含推理结果的定义

  int main() {
      // 配置推理选项
      deploy::InferOption option;
      option.enableSwapRB();  // 启用通道交换（从BGR到RGB）

      // 初始化模型
      auto model = std::make_unique<deploy::DetectModel>("yolo11n-with-plugin.engine", option);

      // 加载图片
      cv::Mat cvim = cv::imread("test_image.jpg");
      deploy::Image im(cvim.data, cvim.cols, cvim.rows);

      // 模型预测
      deploy::DetResult result = model->predict(im);

      // 可视化（代码省略）
      // ...  // 可视化部分代码未提供，可根据需要实现

      // 克隆模型并进行预测
      auto clone_model = model->clone();
      deploy::DetResult clone_result = clone_model->predict(im);

      return 0;  // 程序正常结束
  }
  ```

更多部署案例请参考[模型部署示例](examples) .

## <div align="center">🖥️ 模型支持列表</div><div id="support-models"></div>

<div align="center">
    <table>
        <tr>
            <td>
                <img src='assets/yolo-detect.jpeg' height="300">
                <center>Detect</center>
            </td>
            <td>
                <img src='assets/yolo-segment.jpeg' height="300">
                <center>Segment</center>
            </td>
        </tr>
        <tr>
            <td>
                <img src='assets/yolo-pose.jpeg' height="300">
                <center>Pose</center>
            </td>
            <td>
                <img src='assets/yolo-obb.jpeg' height="300">                                
                <center>OBB</center>
            </td>
        </tr>
    </table>
</div>

符号说明: (1)  ✅ : 已经支持; (2) ❔: 正在进行中; (3) ❎ : 暂不支持; (4) 🟢 : 导出自行实现，即可推理. <br>

<div style="text-align: center;">
  <table border="1" style="border-collapse: collapse; width: 100%;">
    <tr>
      <th style="text-align: center;">任务场景</th>
      <th style="text-align: center;">模型</th>
      <th style="text-align: center;">CLI 导出</th>
      <th style="text-align: center;">推理部署</th>
    </tr>
    <tr>
      <td>Detect</td>
      <td><a href="https://github.com/ultralytics/yolov3">ultralytics/yolov3</a></td>
      <td>✅</td>
      <td>✅</td>
    </tr>
    <tr>
      <td>Detect</td>
      <td><a href="https://github.com/ultralytics/yolov5">ultralytics/yolov5</a></td>
      <td>✅</td>
      <td>✅</td>
    </tr>
    <tr>
      <td>Detect</td>
      <td><a href="https://github.com/meituan/YOLOv6">meituan/YOLOv6</a></td>
      <td>❎ 参考<a href="https://github.com/meituan/YOLOv6/tree/main/deploy/ONNX#tensorrt-backend-tensorrt-version-800">官方导出教程</a></td>
      <td>✅</td>
    </tr>
    <tr>
      <td>Detect</td>
      <td><a href="https://github.com/WongKinYiu/yolov7">WongKinYiu/yolov7</a></td>
      <td>❎ 参考<a href="https://github.com/WongKinYiu/yolov7#export">官方导出教程</a></td>
      <td>✅</td>
    </tr>
    <tr>
      <td>Detect</td>
      <td><a href="https://github.com/WongKinYiu/yolov9">WongKinYiu/yolov9</a></td>
      <td>❎ 参考<a href="https://github.com/WongKinYiu/yolov9/issues/130#issue-2162045461">官方导出教程</a></td>
      <td>✅</td>
    </tr>
    <tr>
      <td>Detect</td>
      <td><a href="https://github.com/THU-MIG/yolov10">THU-MIG/yolov10</a></td>
      <td>✅</td>
      <td>✅</td>
    </tr>
    <tr>
      <td>Detect</td>
      <td><a href="https://github.com/ultralytics/ultralytics">ultralytics/ultralytics</a></td>
      <td>✅</td>
      <td>✅</td>
    </tr>
    <tr>
      <td>Detect</td>
      <td><a href="https://github.com/PaddlePaddle/PaddleDetection">PaddleDetection/PP-YOLOE+</a></td>
      <td>✅</td>
      <td>✅</td>
    </tr>
    <tr>
      <td>Segment</td>
      <td><a href="https://github.com/ultralytics/yolov3">ultralytics/yolov3</a></td>
      <td>✅</td>
      <td>✅</td>
    </tr>
    <tr>
      <td>Segment</td>
      <td><a href="https://github.com/ultralytics/yolov5">ultralytics/yolov5</a></td>
      <td>✅</td>
      <td>✅</td>
    </tr>
    <tr>
      <td>Segment</td>
      <td><a href="https://github.com/meituan/YOLOv6/tree/yolov6-seg">meituan/YOLOv6-seg</a></td>
      <td>❎ 参考<a href="https://github.com/laugh12321/TensorRT-YOLO/blob/main/tensorrt_yolo/export/head.py">tensorrt_yolo/export/head.py</a> 自行实现</td>
      <td>🟢</td>
    </tr>
    <tr>
      <td>Segment</td>
      <td><a href="https://github.com/WongKinYiu/yolov7">WongKinYiu/yolov7</a></td>
      <td>❎ 参考<a href="https://github.com/laugh12321/TensorRT-YOLO/blob/main/tensorrt_yolo/export/head.py">tensorrt_yolo/export/head.py</a> 自行实现</td>
      <td>🟢</td>
    </tr>
    <tr>
      <td>Segment</td>
      <td><a href="https://github.com/WongKinYiu/yolov9">WongKinYiu/yolov9</a></td>
      <td>❎ 参考<a href="https://github.com/laugh12321/TensorRT-YOLO/blob/main/tensorrt_yolo/export/head.py">tensorrt_yolo/export/head.py</a> 自行实现</td>
      <td>🟢</td>
    </tr>
    <tr>
      <td>Segment</td>
      <td><a href="https://github.com/ultralytics/ultralytics">ultralytics/ultralytics</a></td>
      <td>✅</td>
      <td>✅</td>
    </tr>
    <tr>
      <td>Classify</td>
      <td><a href="https://github.com/ultralytics/yolov3">ultralytics/yolov3</a></td>
      <td>✅</td>
      <td>✅</td>
    </tr>
    <tr>
      <td>Classify</td>
      <td><a href="https://github.com/ultralytics/yolov5">ultralytics/yolov5</a></td>
      <td>✅</td>
      <td>✅</td>
    </tr>
    <tr>
      <td>Classify</td>
      <td><a href="https://github.com/ultralytics/ultralytics">ultralytics/ultralytics</a></td>
      <td>✅</td>
      <td>✅</td>
    </tr>
    <tr>
      <td>Pose</td>
      <td><a href="https://github.com/ultralytics/ultralytics">ultralytics/ultralytics</a></td>
      <td>✅</td>
      <td>✅</td>
    </tr>
    <tr>
      <td>OBB</td>
      <td><a href="https://github.com/ultralytics/ultralytics">ultralytics/ultralytics</a></td>
      <td>✅</td>
      <td>✅</td>
    </tr>
  </table>
</div>

## <div align="center">📄 许可证</div>

TensorRT-YOLO采用 **GPL-3.0许可证**，这个[OSI 批准](https://opensource.org/licenses/)的开源许可证非常适合学生和爱好者，可以推动开放的协作和知识分享。请查看[LICENSE](https://github.com/laugh12321/TensorRT-YOLO/blob/master/LICENSE) 文件以了解更多细节。

感谢您选择使用 TensorRT-YOLO，我们鼓励开放的协作和知识分享，同时也希望您遵守开源许可的相关规定。

## <div align="center">📞 联系方式</div>

对于 TensorRT-YOLO 的错误报告和功能请求，请访问 [GitHub Issues](https://github.com/laugh12321/TensorRT-YOLO/issues)！

## <div align="center">🙏 致谢</div>

<center>
<a href="https://hellogithub.com/repository/942570b550824b1b9397e4291da3d17c" target="_blank"><img src="https://api.hellogithub.com/v1/widgets/recommend.svg?rid=942570b550824b1b9397e4291da3d17c&claim_uid=2AGzE4dsO8ZUD9R&theme=neutral" alt="Featured｜HelloGitHub" style="width: 250px; height: 54px;" width="250" height="54" /></a>
</center>
