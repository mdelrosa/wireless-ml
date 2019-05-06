# wireless-ml
Research on machine learning in wireless communications.

## Code

Current work:

- Mason:
	- As of 2019-05-06: Replicating results in Ali and Yangyu, "Automatic Modulation Classification Using Deep Learning Based on Sparse Autoencdoers with Nonegativity Constraints." (detailed below).
		- Issues: Getting GNU radio Python dependency installed on Windows proving difficult. Needed to generate radioml dataset to train/validate network.

### Dependencies

For dataset generation, [radioML dataset repo](https://github.com/radioML/dataset), which requires [gnuradio](https://www.gnuradio.org/doc/sphinx/). [Installation of gnuradio](http://www.gcndevelopment.com/gnuradio/documentation.htm) on Windows is not straightforward, but using of Anaconda might simplify process.

## Papers

Formatting of filenames for papers: XXXX_firstAuthorLastName_titleSummary (e.g., 2018_Dorner_DLOverAir)

- Corlay, V, et al, "Multilevel MIMO Detection with Deep Learning," IEEE 2018 52nd Asilomar Conference, Oct 2018. [Link](https://ieeexplore.ieee.org/document/8645519)
	- **Summary**: Using a deep neural network (DNN) with a customized sigmoid function to reduce network complexity, the authors achieve near Maximimum-Likelihood decoder performance on decoding a MIMO channel.
	- **Methods**: Multi-level sigmoid function, DNN, random forest
- S. Dörner et al, "Deep Learning Based Communication Over the Air," IEEE, Feb 2018. ([Link](https://github.com/mdelrosa/wireless-ml/blob/master/Papers/2018_Dorner_DLoverAir.pdf), [Summary Slides](https://docs.google.com/presentation/d/122XdVg9kUqoCtVnBc7acemM5RyVIfHtDeRlXqwHdOQk/edit#slide=id.p))
- A. Ali and F. Yangyu, "Automatic Modulation Classification Using Deep Learning Based on Sparse Autoencdoers with Nonegativity Constraints," IEEE, Nov 2017. ([Link](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8038046))
	- **Summary**: Extends notion of stacked autoencoders (SAE) by leveraging sparsity ([see here](https://web.stanford.edu/class/cs294a/sparseAutoencoder.pdf) for explanation of sparsity in autoencoders) and nonnegativity constraints on the network's hidden layers. Compares performancec of SAE and SAE with extended maximum likelihood estimator to the autoencoder with nonnegativity constraint (ANC) in classifying signals from five different modulation schemes.
	- **Methods**: Stacked Autoencoders (greedy layer-wise training), Sparse Autoencoders, Cumulants (as signal features), KL Divergence (used to express sparsity constraint in loss function).
	- **Comments**:
		- KL Divergence normally used to measure/minimize difference between two probability distributions. Here, KL Divergence is used to minimizing discrepancy between a given hidden layer's average activation and the sparsity constraint.
		- No comments on runtime/viability as a real-time signal classification method. 
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

- Generally better at NP hard problems
	- 1:
		- "Most fertile ground" in resource allocation
		- Channel information provided to operator too low resolution temporally/spatially
		- What do we do in the case of missing/outdated data?
			- Objective function: maximize data rate for everyone
		- What is the state of the art for deep learning in resource allocation in the context of stale/limited data?
	- 2:
		- If I want better resource allocation, then how do I design the pilots to get the desired information from UEs?
	- Figure out if this is a fertile research direction for the next 2-3 years (minimum)
	- Look-up later: basic understanding of how channel state information is provided
		- Anticipate
	- For encoding/decoding: 
- Chatrooms talking about wireless comms research/machine learning?
- Setup Slack
- Trouble with machine learning: tends to be unstructured
	- Already have good classic approaches for feature extraction. Machine-learning 
	- In order to make it effective, need to apply domain knowledge
	- AWGN is well-understood, so machine learning not well-suited. But what about colored noise? Impulses? (What )
	- Good thing about machine learning: only require one architecture which needs its weights updated
		- Less hardware-specific; different specifications can be implemented by software update instead of changing out processor
