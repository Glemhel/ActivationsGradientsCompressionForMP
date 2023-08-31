# ActivationsGradientsCompressionForMP
Code for experiments with activations and gradients compression for model-parallel training:  
[ResNet+CIFAR compresion experiments](mp_compression_resnet_cifar.ipynb)  
[GPT-2 finetuning on Wikitext experiments](gpt2-finetune-compression.ipynb)

Abstract:

Large neural networks require enormous computational resources with large clusters of machines. Model-parallel training, when model is sequentially partitioned between workers, is a popular approach for training large models. Information compression can be applied to decrease workers' communication time, as it is often a bottleneck in such systems. This work explores how simultaneous compression of activations and gradients in model-parallel distributed training setup affects model convergence. We analyze compression methods such as quantization and TopK compression, and also experiment with error compensation techniques. Finally, we try TopK compression with AQ-SGD per-example error feedback approach. We conduct experiments on image classification and language model fine-tuning tasks.
Our findings demonstrate that gradients require milder compression rates than activations. We observe that $K=10\%$ is the lowest TopK compression level, which does not harm model convergence severely. Experiments also show that models trained with TopK compression perform well only when compression is applied during inference. We find that error feedback techniques do not improve model-parallel training compared to plain compression. Finally, when applied with the AQ-SGD approach, TopK compression stronger than with $ K=30\%$ worsens model performance significantly.

