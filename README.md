# JSMA-16-SP--implement
A simple implementation of the Euro S&P 2016 paper titled "The Limitations of Deep Learning in Adversarial Settings." 

Since the descriptions in Section 4 have some subtle differences from that in Section 3, this script selects the version in Section 4. 

The JSMA method can perturb the images to mislead the high-performance model. 
However, when I reproduce the JSMA method, I find JSMA suffers a heavy time cost from Algorithm 3, i.e., increasing pixel intensities saliency map. 
<img src="Algorithm 3.png"/>

For an MNIST image with size 28x28x1, Algorithm 3 needs to iterate over all possible pixel combinations, i.e., $(28^2 * 28^2 - 28^2))/2 = 306936$. 

The authors claimed they balanced these factors to craft adversarial samples against the DNN in **less than a second**. 

But in my implementation, it takes at least a dozen minutes to perform an attack. 

I can not think of a faster way to solve the problem, so I open the code for help or comments.

# Acknowledgements 

When I reproduce the JMSA method, I have referenced the following articles. 

[Adversarial Attacks - Breaking and defending neural networks](https://deepnotes.io/adversarial-attack)

[Jacobian Based Saliency Map implementation](https://discuss.pytorch.org/t/jacobian-based-saliency-map-implementation/75303/2)

