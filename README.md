当你部署prometheus,crd资源时出现如下报错:
The CustomResourceDefinition "prometheuses.monitoring.coreos.com" is invalid: metadata.annotations: Too long: must have at most 262144 bytes
请执行此命令进行规避： kubectl apply -f crd.yaml --server-side=true 
#--server-side=true
参数的意思是服务器端应用既是原有 kubectl apply 的替代品， 也是控制器发布自身变化的一个简化机制。
如果你启用了服务器端应用，控制平面就会跟踪被所有新创建对象管理的字段。