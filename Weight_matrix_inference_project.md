**Weight matrix inference in spiking EI neural networks demonstrate the need for biologically realistic RNNs for functional connectivity inferences**

G.R. Heller

**Abstract**

Understanding neural networks in a generalizable way is dependent on knowing both what the network activity is (what the dynamics are) and how that activity is generated from the properties of the underlying units (connectivity patterns and strengths). Weight matrix inference from functional activity is a possible mechanism to generate such generalizable models, however inferring valid connectivity from activity alone faces many obstacles and the technique is often misapplied to inappropriate data types using insufficient techniques. We studied weight matrix inference in a spiking EI network in order to gain insight into the feasibility of this technique in a more biologically realistic network. We propose that biologically realistic features such as spiking, obeying dales law, realistic refractory periods and action potential propagation times make weight matrix inference a more tractable problem. We further propose that alternate methods of investigating connectivity such as EM, paired sub threshold recordings and trans-synaptic viral transfection are doomed to fail in capturing the true nature of network connectivity, and that the way forward requires using these techniques to constrain sophisticated, biologically realistic models that can be fit to functional data.

**Introduction**

**Connectomics**

It is not a new idea that knowing the connectivity between neurons is vital to understanding neural networks. Anatomists have relentlessly pursued connectome data for increasingly complex organisms - beginning with the nematode C.Elegens, and more recently obtaining the full connector for the fly - Drosophila Melanogaster. Partial connectomes of unprecedented size are being pursued in mammals, with an enormous dataset of 1mm x 1mm from mouse visual cortex imminent from the Allen Institute, and similar attempts underway with human (I'm not sure about primates....) These datasets have led to some of the most thorough understanding of neural circuitry - understanding the motor and sensory systems of the nematode, verifying linear integrator mechanism in the goldfish oculomotor system, verifying the existence of theorized ring network in the Drosophila head direction system, and proposing new models for the Drosophila forward model to achieve appropriate goal directed flying behavior.

However these methods are excruciatingly difficult,  expensive and time consuming often resulting in the connectome of only a single example organism, and in many ways fall short. We have had the full connector for C.Elegens for 27 years ad have still failed to account for the entire behavioral repertoire. This is likely because the connectome fails to capture meaningful aspects of the connection strength like NMDA/AMPA balance and STP (in truth it barely captures synapse strength at all relying completely on spine size and vesicle density). It also fails to account for additional mechanisms of neural communication (like neurohormones in the example of the worm, or neuropeptides in mammals) and it also provides no information on actual the activity of those neurons in vivo. 

**Functional Activity**

On the other side of the equation are systems neuroscientists who seek to understand the system based on the functional activity of neurons in vivo, and there correspondence to the inputs or outputs of the systems (as controlled inputs to the sensory system and behavioral outputs from the motor system). These attempts often often feel unsatisfactory to me - explaining what the activity is in the form of tuning curves, stimulus response patterns or latent manifolds with little insight into the mechanism of how the neurons generated those responses. They also have little generalizability, making only speculative predictions about the expected activity under different conditions (i.e. VIP neurons activity seem increases to help detect low contrast images so we hypothesize that they may increase activity to discriminate very similar images, or unfamiliar images to which the system has not optimized recognition).  

Without quantatitive generative models of the recorded activity such hypothesis remain poorly defined making few claims about specific timing, interactions or specific 

and often simplifying complex phenomena involving many subclasses of cells to binary predictions of "more" or  "less" activity from a single subclass. Or at best they propose flow chart style node and arrow diagrams of varying complexity as "models." Such hypotheses often amount to little more than speculation as is evidenced by how often they fail to generalize and turn out to be wrong. This is in many ways convenient because it allows systems neuroscientists to endlessly go from experiment to experiment in a way that does little to actually improve the precision and generlizability of the hypotheses they generate.

**Computational models of neural activity**

This is perhaps a bit unfair to many systems neuroscientist who do their best to discover generalizable mechanisms at the level of subclasses or portions, however I still maintain that we can do much better than that in terms of measurable model accuracy and generalizability. In particular recent attempts to (citation, dicarlo, mcdermott, soya etc) explain neural activity at various resolutions (single cell or fMRI) using convolutional neural nets are far more quantifiable in terms of accuracy and generalizeabilty. However these authors are generally quite careful to emphasize that their models are not intended to capture the mechanism that the brain actually uses to generate these responses, but rather that they explain the activity of the neuron or voxel as a complex function of the inputs. The brain computes the same function for the given inputs, but it likely does so in a different way. While being able to predict a quantifiable response is valuable, I propose that such models will likely be much more generalizable if they accurately capture the actual mechanism that the brain uses to produce the responses.

**Estimated Connectivity**

Bridging these 3 sub-domains of neuroscience is the field of "Estimated connectivity" (eC) where authors attempt to infer the connectivity of neurons based on the functional data alone. Some accompanying theoretical work on the process of "weight matrix estimation" shows that this is at least in theory possible for certain conditions of the underlying network, and the method and extend of the activity data. However other theoretical work shows that current eC attempts are impossible and therefore likely misguided and misleading. This is due to a number of confounds that make the inference impossible - the poor spatial and temporal resolution of the data eC is often applied to, confounding effects of highly correlated neurons, confounding effects of unseen neurons and unobserved variables (like state).

In this study we investigate the possibility that using more biologically realistic neural networks may avoid these confounds. More specifically we propose that spiking EI neural networks with biologically realistic action potential propagation times will lead to more accurate weight matrix inferences. Due to the chaotic nature of the networks (citation), they should traverse a larger activation space than patterned networks (as in citation) which will lead to disambiguation of spuriously correlated but unconnected pairs. The spiking nature and the delayed AP propagation will provide better temporal resolution and additional constraints on what activity comes is due to correlations and what is due to causation. Lastly, using an EI network will increase the utility of the model - even if we cannot eliminate errors weight strength, identifying the subclass of functionally recorded neurons will be a useful output of such models (all models are wrong, but some are useful).

We will then discuss the theoretical confounds that have been raised in more detail, and attempt to outline a path toward more accurate estimated connectivity. We propose that this goal requires fitting biologically realistic models (but not biophysically detailed) to appropriately extensive in-vivo data.

**Results**

We first generated spiking data from a balanced EI network based on (citation). By looking at the spike rates of the neurons, we can see that this does indeed exhibit chaotic dynamics. (Fig 1x) However when we zoom in on the spiking patterns of the neurons we can instantly see that they have departed from biology in an important way - there is no evidence of a refractory period (Fig1 x). While it is possible that this will not effect our ability to infer the weight matrix, it is also possible that this will be detrimental or at best make our results misleading. In a typical extracellular electrophysiology recording you are sampling at 30kHz - and have potentially even higher temporal resolution by interpolating and aligning the waveform to estimate the true start/peak of the action potential. Depending on the cell type, and how you consider the samples of the action potential itself the refractory period of a neuron can be anywhere between 1-4 ms or even longer. Considering the conservative case of 1ms, there are 30 samples during which spikes from other neurons could occur. This temporal resolution is drastically different from what is observed in this model, and this could feasibly change the inferred relationship between two simultaneously spiking neurons, potentially drastically decreasing the number of spike correlate spikes required to introduce spurious correlations (need a diagram to illustrate this).

Next we observed the inter-unit interactions by plotting the cross correllogram of spike times. This visualization is commonly used in spike sorting to identify merges and splits, but also has implications for functional connectivity (Fig 1x, from citation). Short latency (~3 ms) sharp peaks could be indicative of synaptic connectivity. While there are certainly architectures that could lead to the same latency interactions (need diagram) the sharp peak is certainly compelling. (Would be nice to do some additional investigation of specifically this architecture to see if we can disambiguate). Thus, we investigated our data for the presence of sharp peak interactions between pairs of neurons. (Fig1x) While it is clear that some of these pairs exhibit biologically plausible relationships, it was again immediately clear that timescale of the interactions was not appropriate. After observing the code, I confirmed that there was was only a 1 timestep delay in between spike initiation in a pre-synaptic neuron and spike receipt in a post-synaptic neruon. Typical action potential propagation is around 3ms depending on the cell type and myelination and length of the axon. Depending on the time constant and the chosen dt, this could result in wildly unrealistic dynamics. As before, it is possible that this increased speed of interactions would not affect our ability to infer the weight matrix, but the opposite is also possible - that because the interactions are effectively compressed you lose temporal resolution to disambiguate co-uccuring but unrelated interactions (need a diagram).

Despite making these observations, given time constraints we decided that the best course of action was to continue probing the network that was already exhibiting the minimum desired behavior (spikes and chaotic dynamics) rather than try to pursue a more realistic model that might require additional debugging and parameter tweaking to get things working. Sadly attempting to run the spiking out put through an off the shelf GLM failed to return weight estimates, returning all zeros for the spiking input and all NANs for the rates. This could be for many reasons, but rather than attempt to troubleshoot, I decided my time would be better spent reading additional sources and writing a thorough discussion since that would be a guaranteed good return on my time. Given more time, I would really like to compare the weigh matrix inference for a 5 different networks original spiking, refractory spiking, action potential propagation, both refractory and propagating and a smoothed version of the best spiking network. If this works, it could be a powerful statement that for some use cases, biological realism really does matter - in particular getting the spiking right. It would also be nice to go through all the toy architectures that I pull from the literature in the discussion and run them quantitatively (with some noise and various strengths) and show that we can in fact infer the correct motif rather than just relying on the thought experiment.

**Discussion**

If the results of weight matrix  inference align with our hypothesis, we would use the first part of the discussion to reinforce the necessity of using appropriately sophisticated and biologically realistic networks when investigating weight matrix inference. Given this, it is possible that much of the existing theoretical literature has not used models that are well suited to give accurate assessments of how weight matrix inference would work when applied to real (and appropriately spiking) neural data.

Thus we would like to address the counter arguments proposed in the literature and think about whether they would hold for a biologically realistic network.

**Resolution Issues: Temporal resolution and neuronal averaging confound eC**

One issue raised in the literature is that of resolution, both temporal resolution that causes multiple action potentials to be grouped together and measured in a single sample, and spatial resolution that requires multiple neurons to grouped together in a single pixel/voxel. Two sources of functional data that are often subject to estimated connectivity style analyses are fMRI data and population calcium imaging. fMRI in particular has low spatial and temporal resolution. A single voxel can contain the activity of hundereds of neurons, and a single sample can contain dozens of spikes from each of those neurons. This clearly confounds the inference of connectivity, and is firmly in the realm of "time shifted correlations." Calcium imaging has single cell spatial resolution, but it still has low temporal resolution because of the nature of the calcium signal and constraints of the sensor. Typical calcium imaging is done at ~10hz which is clearly quite slow, a single sample can contain multiple spikes, meaning that even with extensive data it will be impossible to disambiguate causation. We can easily imagine one cell that fires a burst of spikes and induces firing in another cell. A neuron bursting at 250hz could fire 10 spikes spikes in a 40ms. Any downstream response within 60ms would still be contained in the 100ms sampling of the same frame that detected the activity of the presynaptic neuron.  (see fig 4).  In certain cases it is possible to deconvolve spike trains from calcium imaging acquired at say 100hz, this is certainly more promising. However being able to identify that a spike has occurred and identifying exactly when it occurred are two different issues and it seems like the temporal resolution of deconvolve spikes is still quite low (personal communication, Peter Ledochovich, should find this paper) which leads again to ambiguous ordering of spikes from paired neruons (figur 4). It is worth noting that there are plenty of imaging techniques capable of recording at Kilohertz sampling rates and thereby having sufficient temporal resolution to be useful for models of functional connectivity, and voltage sensors are progressing rapidly. When population level voltage imaging it may be useful for weight matrix inference, however for the foreseeable future it will still have much lower temporal resolution than extracellular electrophysiology. Therefore spiking data and spiking models are really the only ones that should even be considered for this endeavor.

**Correlation Issues: Highly correlated activity confounds eC**

Even in the best case scenario where you can record ever neuron in the network there are some networks for which weight matrix inference is still intractable (citation). The authors show that for strongly recurrent networks (r>.15) no amount of data will be able to eliminate spurious connections resulting from high correlations. While this is important to keep in mind, there are a number of reasons why this might not be truly problematic for eC. The authors themselves note that by providing a suppressive drive to the system can be forced into a low activity state where the correlations dissolve. This could be accomplished with anesthesia, optogenetics, or may even happen naturally in sleep. So simply observing the network in the appropriate state may eliminate this confound completely.

Secondly, while they have matched the level of recurrent connection strength with estimated values from the human brain, it seems unlikely that the brain will have quite this level of correlation. Even in memory areas I have never seen any activity in mammals that looks quite this robust, and it is also questionable whether the brain would implement such a mechanism since extremely high correlations are in some sense unnecessary redundancy.

Thirdly, the inference is still rather good. While unsatisfying to the authors, I think this level of accuracy would still lead to quite valuable insights and the ability to generate verifiable hypotheses.

Lastly, intuitively spiking should actually take care of this because we would not expect correlations to hold to such rigid correlations on sub-millisecond timescales (see fig 5), and I'm very curious to see exactly what the authors used. Its possible the same temporal resolution issues with refractory period and action potential propagation would apply here.

This all amounts to the conclusion that correlations are not necessarily a deal breaker for eC, however that does not mean we can ignore about this potential confound. Any attempt to estimate connectivity should also attempt to estimate how correlations would affect the inferred connectivity in the model of choice, and assess when multiple equivalent weight matrices could equally predict the observed activity.

**Unobserved Variables: Hidden neurons and hidden states confound eC**

Figure 6

The state image in "the lure paper" - diagram of spiking times

specific 3 neuron network

the image in the estimating hidden effects (longer chains)

The final, and largest confound for eC is the presence of unobserved neurons or unobserved variables (states) that change the. We will address the confound of unobserved states first since it is slightly more straightforward. 

**Hidden states**

The confound is expressed will in Figure 6, taken from Mehler and Kording. A change in state drastically changes the relative firing rates of neurons A and B, however an increase in firing rate of of neuron B still increases the firing rate of neuron A. When considering things in a a spiking context where typical firing rates in-vivo range between 1 and 100 hz, it is not clear that this confound would be at play at all. The average firing rates of the neurons involved are not really important to inferring the connections. In the first state there are many spikes from neuron A that are temporally distant from the spikes of neuron B (distant being approximately >20ms apart) and therefore irrelevant. In the second state the opposite is true. But in both states if there is a real influence of Neuron B on Neuron A then we should still be able to observe the increased spiking probability of neuron A following spikes from neuron B (within approx 20 ms).

Again, this is not to say that we should ignore state variables. Including as much state information in the model as possible should help fit the models when the state information could not have easily been inferred from the spiking data. This should certainly include LFP which often comes for free alongside extracellular recordings, but could also include measurements like pupil diameter, heart rate, breathing rate and even paired whole brain recordings from other modalities like eeg (cite leslie clarr), ecog or wide field imaging. In some sense the environmental input (often considered the sensory stimulus) and the motor output should also be included as additional information that can predict "state" variables as well as as neuronal firing rate. We will discuss this more when comparing to Pillow and Latham 2008.

**Hidden Neurons**

In smaller systems like the worm, fly or zebrafish it is possible to observe every neuron in the network both functionally and anatomical. For mice and other mammals this is not possible with current tools, especially not with extracellular electrophysiology. This means that there will inevitably be neurons that we do not record, and these neurons form synapses with the ones that we do record. This confound is well known (Citation, citation) and unavoidable. However we propose that it is not necessarily a nail in the coffin for eC. For the toy examples given by Brinkmann and Buice spiking with sufficient temporal resolution gives us a clear solution figure 6). Due to the action potential propagation time, the effect of 1 neuron on another will be isolated in the interval between 3 and 6 milliseconds, while all the downstream effects that rely on additional intervening neurons will take longer (figure 6).

We can, however easily imagine other architectures for which spiking does offer a solution (figure 7). This architecture in particular I think deserves more theoretical attention. It is possible that you could still disambiguate the two situations but it is not clear to me exactly how well. However, the false connection is not completely correlational. It is representative of a different path. If Neurons B and D are the same type and fulfill the same network role, this false connection will likely generalize appropriately and will not interfere with the end goal of eC. If B and D are not the same type then we may be able to identify that the connection is false if we can correctly identify that B is not the type of cell that would interact with a cell of type A in this way (ie if we know B is excitatory and the inferred connection is inhibitory we can infer the presence of C and D).

Figure 7

Diagram of the cases where we still have issues - 

one unseen neuron drives a seen and unseen

connection masked by inhibition

**Hidden neurons: Just how many can be missing?**

As we move beyond toy models with few neurons, the missing neuron problem becomes increasingly problematic. With more and more potential missing links and alternate paths, it seems almost inevitable that obstruction of the real connectivity will occur. Mehler and Kording state the following: "the number of recorded neurons is a vanishingly small subset of all neurons ... we should expect that the parts of neural activity driven by unobserved neurons are arbitrarily larger than the parts coming from observed neurons." Brinkmann and Buice follow up with the theoretical demonstration that especially for networks with strong synaptic weights there is considerable detriment to the inferred weights. It is not completely clear to me that we expect real brains to fall into this category - and this could also be species specific. Human post-synaptic potential often illicit spikes in paired patch experiment in slice (personal communication stephanie Seeman, allen institute) while this rarely occurs in mouse. Its further possible that state dependent effects that lower the average firing rate of all the neurons would "weaken" the relative strength of each synapse, moving the network to the tractable zone (connections scaling with 1/N).

Another consideration here is that while we cannot hope to record from all the neurons in the network, we CAN imagine recording from all the presynaptic partners of a given neuron (sur lab would like to do this by imaging the axon terminals, and I might be the one to do it). We can also imagine recording from a large portion of the first order synaptic partners using soon to be available extracellular recording techniques. The Allen institute's existing recording technique targeting 6 neuropixels probes to the retinotopic center of 6 different visual areas increases the probability of finding connected pairs because neurons preferentially connect to others that process the same portion of visual space. While it is unlikely that the current recordings are sufficient advances are right around the corner. Neuropixels probes with 4 shanks each could effectively quadruple the number of neurons recorded in the relevant portion of visual cortex. We can also imagine leaving 1 probe implanted chronically and performing paired recordings as suggested by many of the theoretical work that proposes to solve the hidden neuron problem in this way (citation). Eventually it might be possible to sample a sufficiently large portion of the presynaptic partners for a subset of the units on the chronically implanted probe that a reasonably accurate connectivity could be inferred. We see this as the best route forward for estimated connectivity, along with additional theoretical work using increasingly biologically sophisticated models to flesh out the constraints of weight matrix inference.

**Integration with post-mortem measures of connectivity**

While it is clear that functional connectivity has its limitations, as we noted in the introduction, post mortem measures of connectivity fall short in many ways as well. While EM does a great job of identifying connected neurons and where the synapses are on the dendritic tree, but is currently able to identify long range connections. It also gives only limited estimates of synaptic strength, and doesn't offer any information about the short term plasticity of the synaps. Paired cell recordings (either patch, or more recently patch-optical and all optical optopatch) can also identify connected neurons, and perhaps estimate some of the synaptic plasticity parameters, but they currently struggle to identify where the synapse is, and also struggle with very low throughput and long range connections. Tans-synaptic viruses do a good job of identifying connected neurons, but is limited to 1 neuron at a time if you want an unambiguous pair of neurons. Trans-synaptic viruses could also potentially elucidate the strength and STP of each synapse functionally but this has not been done to my knowledge and would in any case be even lower throughput than the post-mortem methods.

We propose that these post-mortem methods should be used to constrain the model space that we use to fit to the functional data. If we know the connection probability between different cell types (EM and slice), the location constraints on those synapses (from EM), the range of possible synaptic properties (from slice), and the typical response properties of the cell type (from functional characterization) then we can drastically constrain the model that we attempt to fit to the eC data.

This also requires developing sufficiently complex models that capture these parameters. Attempts to build biophysically detailed models (Allen institute visual cortex model and blue brain project) are certainly complex enough, but to my knowledge they are not designed to be "fit" to data, and this complexity will likely work against them. We should work towards models that can adequately capture the known relevant phenomena: spiking, AP propagation time, refractory periods, variable distances between synapses and soma, multiple time constants for synapses and multiple forms of STP. These models can then be interrogated to using weight matrix inference to estimate the limitations of fitting such models to incomplete data, and also importantly to elucidate which stimuli are the most useful to traverse the activity space and reveal real connections. (stimuli here including uninvasive sensory inputs as well as invasive inputs like optical, chemical, electrical or magnetic activation or deactivation). While this is an enormous endeavor, research in this direction seems to me to truly be the most promising way to generate real, generalizable models of the brain and approach something that we may be able to call "understanding".

**References**

Emmons, S. W. (2015). The beginning of connectomics: A commentary on White et al. (1986) 'The structure of the nervous system of the nematode Caenorhabditis elegans.' In *Philosophical Transactions of the Royal Society B: Biological Sciences* (Vol. 370, Issue 1666). Royal Society of London. <https://doi.org/10.1098/rstb.2014.0309>

Siegle, J. H., Jia, X., Durand, S., Gale, S., Bennett, C., Graddis, N., Heller, G., Ramirez, T. K., Choi, H., Luviano, J. A., Groblewski, P. A., Ahmed, R., Arkhipov, A., Bernard, A., Billeh, Y. N., Brown, D., Buice, M. A., Cain, N., Caldejon, S., ... Koch, C. (2021). Survey of spiking in the mouse visual system reveals functional hierarchy. *Nature*, *592*(7852), 86--92. <https://doi.org/10.1038/s41586-020-03171-x>

Das, A., & Fiete, I. R. (2020). Systematic errors in connectivity inferred from activity in strongly recurrent networks. *Nature Neuroscience*, *23*(10), 1286--1296. <https://doi.org/10.1038/s41593-020-0699-2>

Li, Q., & Pehlevan, C. (2020). *Minimax Dynamics of Optimally Balanced Spiking Networks of Excitatory and Inhibitory Neurons*. [*http://arxiv.org/abs/2006.08115*](http://arxiv.org/abs/2006.08115)

Brinkman, B. A. W., Rieke, F., Shea-Brown, E., & Buice, M. A. (2018). Predicting how and when hidden neurons skew measured synaptic interactions. *PLoS Computational Biology*, *14*(10). <https://doi.org/10.1371/journal.pcbi.1006490>

Marc, D., Mehler, A., & Kording, K. P. (n.d.). *The lure of misleading causal statements in functional connectivity research*.