# 网络资源优化简介
简介：神经网络模型的训练可分为集中式和分布式，集中式需要将数据聚合在数据中心进行训练，分布式机器学习系统利用网络中的设备和资源来训练神经网络模型。

在联邦学习中，模型聚合在服务器上进行，通过平均局部模型更新生成全局模型。在FL的整个训练过程中，只有模型参数在客户端和服务器之间进行通信。因此，客户端不需要将其原始训练数据共享给服务器或其他客户端，本地数据保持在本地且保密。然而，训练整个模型通常对计算要求太高，并且可能导致在资源受限的设备上训练时间过长。

在拆分学习中，将神经网络从一个特定的层（分割层或切割层），神经网络被分成两个子网络。第一部分部署设备端，第二部分部署在服务器端。训练时，模型被训练到分割层，然后将分割层的特征发送到服务器；服务器继续训练直到模型的最后一层；在计算出训练损失并更新梯度后，将分割层的各个中间梯度发送到设备，以便在设备上更新梯度。上述过程在整个客户端数据集上的迭代通常称为训练轮。反复进行训练多个轮次，直到模型收敛。

研究基于联邦拆分学习在资源受限的设备中高效计算。