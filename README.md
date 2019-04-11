# wireless-ml
Research on machine learning in wireless communications.

## Papers

Formatting of filenames for papers: XXXX_firstAuthorLastName_titleSummary (e.g., 2018_Dorner_DLOverAir)

- S. Dörner et al, "Deep Learning Based Communication Over the Air," IEEE, Feb 2018. ([Link](https://github.com/mdelrosa/wireless-ml/blob/master/Papers/2018_Dorner_DLoverAir.pdf), [Summary Slides](https://docs.google.com/presentation/d/122XdVg9kUqoCtVnBc7acemM5RyVIfHtDeRlXqwHdOQk/edit#slide=id.p))
- S. Peng et al, "Modulation Classification Based on Signal Constellation Diagrams and Deep Learning," IEEE Transactions on Neural Networks and Learning Systems. Mar 2019. ([Link](https://ieeexplore.ieee.org/document/8418751))
	- **Summary**: Performs signal modulation classification by applying image-like segmentation of constellation diagrams to make data compatible with well-established convolutional neural networks (CNN), including [AlexNet](https://medium.com/@smallfishbigsea/a-walk-through-of-alexnet-6cbd137a5637) and [GoogLeNet](https://ai.google/research/pubs/pub43022). Demonstrates DL-based classification accuracy exceeds that of other traditional classification methods (i.e., cumulant-based statistics).
	- **Methods**: Deep Learning, Convolutional Neural Networks, Image Processing. 
	- **Upshot**: DL-based classification of most low-order modulation schemes (i.e., BPSK, ASK) is high, but accuracy for higher order schemes (e.g. 16/64 QAM) suffers (74.1%/68.3%, respectively). Additionally, DL/CNN approaches demand more computation time than traditional methods (see Table III). Does not seem like paper attempts classification on live, OTA data.
- T. O'Shea, T. Roy, T. Charles, "Over-the-Air Deep Learning Based Radio Signal Classification," IEEE Journal of Selected Topics in Signal Processing. Feb 2018. ([Link](https://ieeexplore.ieee.org/abstract/document/8267032), [Radioml Github](https://github.com/radioML))
	- **Summary**: Demonstrates residual neural network (RNN) which is capable of discerning different radio modulation schemes with better accuracy (?) than previously developed convolutional neural networks and other baseline methods. Applies RNN to OTA data and demonstrates feasibility of deep-learning based signal classification.
	- **Methods**: Deep Learning (residual neural networks, transfer learning). 
	- **Upshot**: Transfer learning valuable but does not achieve equivalent accuracy/sensitivity compared to direct training when transfer learning data is small. Transfer learning can be made more valuable when simulation methods become more accurate, allowing for generation of synthetic data which accurately represents real-world data.
- H. Mao et al, "Resource Management with Deep Reinforcement Learning," HetNets, Nov 2016. ([Link](https://people.csail.mit.edu/alizadeh/papers/deeprm-hotnets16.pdf), [GitHub](https://github.com/hongzimao/deeprm))
	- **Summary**: Presents a deep reinforcement learning algorithm, "DeepRM," which learns sensible online scheduling of multiple computational resources by minimizing average slowdown in each timestep. Demonstrates experimental performance gains over other scheduling algorithms.
	- **Methods**: Reinforcement learning (policy-gradient methods, REINFORCE). Deep Learning. 
	- **Upshot**: Not strictly a wireless communications or deep learning application, but demonstrates discsussion of scheduling and online learning might prove useful in analogous wireless communications network application, such as cluster scheduleing/formation in 5G networks.
- S. Jiang et al, "VIA: Improving Internet Telephony Call Quality Using Predictive Relay Selection," SIGCOMM, Aug 2016. ([Link](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/08/via.pdf))
	- **Summary**: Uses machine learning to improve Quality of Experience (QoE) for VoIP by combining methods from overlay networks and reinforcement learning. Demonstrates theoretical and experimental reduction in metrics of Poor Network Rate (PNR), including round-trip time (RTT), packet loss, and jitter.
	- **Methods**: Reinforcement learning (multi-armed bandit, Upper-confidence bound, epsilon-greedy). Overlay networks.
	- **Upshot**: Not strictly a wireless communications or deep learning application, but demonstrates methods which might prove applicable.

