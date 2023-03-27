# widget_perviewer

[English](./README.md) | [简体中文](./zh.md)

## 编译

`widget_perviewer`=`widget_previewer -pre` + `flutter_demo_previewer -pre` 推荐直接获取最新仓库代码.

```bash

### 不推荐
git clone https://github.com/zhangwb1996/widget_previewer.git --recursive

### 推荐 
mkdir widget_perviewer
git clone https://github.com/zhangwb1996/flutter_demo_previewer.git -pre
git clone https://github.com/zhangwb1996/widget_design.git -pre
# 用VSCode或者其他IDE打开
code . 
# 更新依赖
flutter pub get
# then
cd flutter_demo_previewer

### 新增依赖平台的代码(linux, windows, macOS)
flutter create -platform=windows .

### 运行flutter_demo_previewer项目下的main.dart

```

## 如何自建demo

* 把demo放到`widget_design/lib/src/preview`这个路径下(具体位置随意)。
* **把demo需要入口类放到第一个**.
* A sample example this:

    ```dart
    // put yout target class at the first of all class in your single file
    class TargetClass extends StatefulWidget {
        ...
    }
    class ClassA {
        ...
    }
    class ClassB  {
        ...
    }
    class ClassC {
        ...
    }
    ```

* **Add export into `widget_design/lib/src/preview/widget.dart`**

    ```dart
    export 'file.dart' show TargetClass
    ```

* Run below command at you terminal

    ```shell
    dart cd flutter_demo_previewer

    # generate _builder.dart files
    dart ./lib/tools/dir/dynamic_widget_helper.dart pre

    # clean and regenerate all the _builder.dart files
    dart ./lib/tools/dir/dynamic_widget_helper.dart clean
    dart ./lib/tools/dir/dynamic_widget_helper.dart pre
    ```

* **不支持热更新**. 需要重启app.

## Release

> **把Release解压到和`widget_design`项目相同的目录**

(科学上网预览下面的gif)

![WDP](https://github.com/zhangwb1996/screenshot/blob/main/WDP/WDP.v1.0.0.gif)

## Awesome Packages

| Pub | Repository |
| ----|---- |
| [json_dynamic_widget](https://pub.dev/packages/json_dynamic_widget)         | [json_dynamic_widget](https://github.com/peiffer-innovations/json_dynamic_widget)
| [provider](https://pub.dev/packages/provider)                               | [provider](https://github.com/rrousselGit/provider)
| [flutter_treeview](https://pub.dev/packages/flutter_treeview)               | [flutter_treeview](https://bitbucket.org/kevinandre/flutter_treeview/src/master/)
| [flutter-code-editor](https://pub.dev/packages/flutter_code_editor/install) | [flutter-code-editor](https://github.com/akvelon/flutter-code-editor)
| [highlight](https://pub.dev/packages/highlight)                             | [highlight](https://github.com/git-touch/highlight.dart)
| [Blur](https://pub.dev/packages/blur)                                       | [Blur](https://github.com/jagritjkh/blur)
