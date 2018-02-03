# GAN-MNIST
Udacity Deep Learning Foundation Nanodegree Program(DLND)  
Part.5 Generative Adversarial Networks Lesson about GAN on the MNIST data set.  
  
This is my solution for Udacity DLND project about GAN.  
https://github.com/udacity/deep-learning/tree/master/gan_mnist  
  
  
The solution provided by Udacity use "tf.layers.dense" to build the generator and discriminator,  
on the other hand my solution use "tf.add(tf.matmul(input, weight), biases)".  
  
In this solution, we need to use tf.get_variable('name', initializer), not tf.Variable().  
If we use tf. Variable, we get multiple weight and biases as below.  

 ####<tf.Variable 'discriminator/Variable:0' shape=(784, 128) dtype=float32_ref>,  
 <tf.Variable 'discriminator/Variable_1:0' shape=(128, 1) dtype=float32_ref>,  
 <tf.Variable 'discriminator/Variable_2:0' shape=(128,) dtype=float32_ref>,  
 <tf.Variable 'discriminator/Variable_3:0' shape=(1,) dtype=float32_ref>,  
 <tf.Variable 'discriminator_1/Variable:0' shape=(784, 128) dtype=float32_ref>,  
 <tf.Variable 'discriminator_1/Variable_1:0' shape=(128, 1) dtype=float32_ref>,  
 <tf.Variable 'discriminator_1/Variable_2:0' shape=(128,) dtype=float32_ref>,  
 <tf.Variable 'discriminator_1/Variable_3:0' shape=(1,) dtype=float32_ref>]  
   
 Reference are as below.
 https://stackoverflow.com/questions/44964691/tf-trainable-variables-returns-more-than-one-graphs-variable
 https://deepage.net/tensorflow/2017/06/02/tensorflow-variable.html
