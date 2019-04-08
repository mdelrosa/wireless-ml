# wireless-ml
Research on machine learning in wireless communications.

## Papers

Formatting of filenames for papers: XXXX_firstAuthorLastName_titleSummary (e.g., 2018_Dorner_DLOverAir)

- S. Dörner et al, "Deep Learning Based Communication Over the Air," IEEE, Feb 2018. ([Link](https://github.com/mdelrosa/wireless-ml/blob/master/Papers/2018_Dorner_DLoverAir.pdf), [Summary Slides](https://docs.google.com/presentation/d/122XdVg9kUqoCtVnBc7acemM5RyVIfHtDeRlXqwHdOQk/edit#slide=id.p))
- H. Mao et al, "Resource Management with Deep Reinforcement Learning," HetNets, Nov 2016. ([Link](https://people.csail.mit.edu/alizadeh/papers/deeprm-hotnets16.pdf), [GitHub](https://github.com/hongzimao/deeprm))
	- **Summary**: Presents a deep reinforcement learning algorithm, "DeepRM," which learns sensible online scheduling of multiple computational resources by minimizing average slowdown in each timestep. Demonstrates experimental performance gains over other scheduling algorithms.
	- **Methods**: Reinforcement learning (policy-gradient methods, REINFORCE). Deep Learning. 
	- **Upshot**: Not strictly a wireless communications or deep learning application, but demonstrates discsussion of scheduling and online learning might prove useful in analogous wireless communications network application, such as cluster scheduleing/formation in 5G networks.
- S. Jiang et al, "VIA: Improving Internet Telephony Call Quality Using Predictive Relay Selection," SIGCOMM, Aug 2016. ([Link](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/08/via.pdf))
	- **Summary**: Uses machine learning to improve Quality of Experience (QoE) for VoIP by combining methods from overlay networks and reinforcement learning. Demonstrates theoretical and experimental reduction in metrics of Poor Network Rate (PNR), including round-trip time (RTT), packet loss, and jitter.
	- **Methods**: Reinforcement learning (multi-armed bandit, Upper-confidence bound, epsilon-greedy). Overlay networks.
	- **Upshot**: Not strictly a wireless communications or deep learning application, but demonstrates methods which might prove applicable.

