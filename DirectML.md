# DirectML适合什么项目？

# Binding 绑定
Binding是指将资源挂载到管线上，以便在初始化和执行机器学习操作时使用。资源可以是输入输出Tensor，也可以是操作需要的临时或持久的资源。
# Dispatchable 可派发的
一个Dispatchable可以是一个操作初始化器或者一个编译好的操作。
# Residency 驻留
在D3D12中，程序员需要自己管理资源的驻留与去除。应用程序应该避免在短时间内，频繁的让一个资源进出GPU。
