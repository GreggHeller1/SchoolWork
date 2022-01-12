Detangling the Jungle of Cells types in mouse primary visual cortex in-vivo

Trying to understand what cells in visual cortex do without access to detailed cell type information is like trying to understand what animals in a jungle do without detailed species information. Imagine for a moment trying to study the dynamics of a jungle (analogous to a neural population) when the only information you have is whether an animal is primarily a predetor or prey (analagous to inhibitory/excitatory distinction), and the movements of that animal (analagous to neuronal activity).  The data would look very messy because the activities of all the snakes is lumped in with the tigers. It wouldn’t be clear whether two animals avoid each other because they are territorial or because they prefer different environments. However once you have meaningful category labels, the important similarities, distinctions and interactions between the behavior of different types becomes clear. 

We can extend this analogy further to demonstrate why imaging of separate cre-lines (as done for the allen institute ophys brain observatory) is insufficient because you lack the meaningful interactions between types - this would be analogous to monitoring one animal type at a time, at a very low temporal resolution and attempting to figure out how they interact with eachother. Perhaps you could identify when an animal was running away based on its velocity, but it would be very hard to know what it was running from.  Clearly it would be much easier to understand meaningful interactions, if you were able to capture the dynamics of both populations with sufficient temporal resolution to actually observe the interactions. Thus, we propose to identify cell types in neuropixels recordings in mouse visual cortex. 

Specific aim 1
To assess the functional interactions between 10 (arbitrary number greater than 3) or more putative subtypes in mouse primary visual cortex during visual stimulation. We will do this by registering cells recorded with a neuropixels probe to a post-mortem imaged volume where cell types have been identified transcriptomically. Visual stimulation and extracellular recording will be designed to replicate the conditions used at the Allen institute for their extensive brain observatory dataset so that results can be compared and contextualized using their ecephys and ophys datasets. 

Specific aim 2
To determine whether better cell type resolution can be obtained for in-vivo recordings without relying on post mortem histological techniques. We will do this using a combination of the following: detailed spatio-temporal information of the extracellular waveform, spike timing relationships, detailed analysis of optogenetically induced spiking, and if necessary functional properties. Using the results of work for specific aim 1 we should be able to verify the effectiveness of these techniques using ground truth transcriptomic information for each unit, and then assess the feasibility of applying them to other previously collected, publicly available datasets like the allen institute’s or the IBLs.Research Strategy
(A) Significance
Towards cell type specific clinical interventions
Most clinical interventions that are currently available are very non-specific. They work or neurotransmitters (e.g. SSRIs), on the level of brain areas (e.g. lesions) or at best a combination of brain areas and frequencies (e.g. deep brain stimulation). Current advances in gene therapies are promising, but will likely only be applicable for a small fraction of disorders that stem from very specific genes. To me this is analogous to trying to fix a laptop with a baseball bat - the level of complexity of the brain is so vast compared to the specificity of our interventions, that it is not the least bit surprising that interventions can be highly variable in their effectiveness, and often have undesirable off target effects. It is clear that interventions with higher specificity could lead to better clinical outcomes. 

One way to increase the specificity of interventions - whether gene based, drug based or stimulation based is to target them to more specific subpopulations of neurons. Indeed, very recently an alternative to non-specific DBS has been proposed that targets PV interneurons and has the potential to be far superior to DBS, with longer lasting effects require less total stimulation (9). However, before cell type specific treatments can be developed we must overcome two obstacles: we must have understand the functional role of different cell types, and we must have a method to access them in live humans. For this proposal we focus on understanding the functional role of cell types with the understanding that others who are better suited are to do so are already working on mechanisms to access these cell type specific subpopulations. 

Cross species compatibility
We have proposed to do this work in mice, since cell type information is more readily available in different modalities (transcriptomic, morphology, electrical (6) and connectivity based (Personal communication, Forest Naylor) . However, one of the reasons we have chosen to focus on extracellular electrophysiology recordings is because of their relevance across species. To our knowledge, simultaneous single unit information has never been been obtained in-vivo in humans in any other way. Furthermore, many of the methods that we propose to use are compatible with recordings in primates and humans. Extracellular waveform and functional properties of spiking have already been used to classify units into 9 putative types in primates. And while neuropixels probes have primarily been used in rodents. they are beginning to be used in primates and have been proposed to be used in human epilepsy patients. This makes it more likely that results of our specific aim 2 will be generalizable to these recordings. 

Post-recording histology would certainly be compatible with human and primate tissue, although because of the rarity of the samples, this would be best used as a mechanism for acquiring ground truth transcroptimic information in order to calibrate and validate the other information modalities as we have proposed. Lastly, while optogentics will likely never be compatible with human or primate recordings, read/write technology of electrodes continues to improve in spatial specificity (i.e. neuralink). It is possible that similar data could be collected using ultra-local electrical stimulation. We believe that this proposal serves as a first step to establish methods in mice that could be used in primates and humans in the future. The ability to confirm whether the circuit works similarly in higher mammals will be very important to determine which cell type specific interventions may also be compatible with higher mammals.

Methods should generalize to clinically relevant brain areas
We have proposed to perform this study in mouse visual cortex because this areas cell types are already thoroughly catalogued in multiple modalities - based transcriptomics, morphology and electrical properties (cite paper). There is also extensive cell type specific function information that could be helpful to validate our findings. Soon there will be unique connectivity information available for primary visual cortex as well thanks to the 1mmx1mm EM dataset (Clay Reid, Princeton unpublished). 

However, we think the methods we have chosen will generalize well to areas that are more commonly associated with psychiatric disorders than visual cortex. It has been shown that inhibitory cell types are largely overlapping in different cortical regions, so it is possible that our techniques to identify inhibitory cell types will generalize with no additional effort. Furthermore, because we have chosen to us extracellular electrophysiology instead of genetic/optical methods, our technique will generalizable much more easily to a wide variety of brain structures, especially those that are difficult to access optically due to depth. 

Conclusion
In conclusion, we believe that using information already easily available in neuropixels recordings to obtain in-vivo cell type classifications holds enormous potential to map functional circuits in a large variety of brain areas, species and disease models. It would be an enormous step towards cell types specific interventions to treat human psychiatric conditions. 

(B) Innovation
Unprecedented cell type specificity in-vivo
To our knowledge, no studies have successfully recorded simultaneously from more than 3 known classes of cells extracellularly. Commonly extracellular datasets can be divided into PV interneurons and non-PV neurons using narrow spiking-vs broad spiking waveform. More recently, optotagging has been used to identify a 3rd class of genetically labeled cells, typically interneurons or neuromodulators to avoid trans-synaptic excitation. However the specificity of optotagging is poorly characterized and it still only adds the ability to access 1 population, possibly a few by using different wavelengths and corresponding rhodopsins. 

If you include layer information that is accessible in recordings with laminar probes and some microscopes, you could increase the your putative cell class classification specificity by a few fold, since most cell types span only 1 or 2 layers. Indeed, there is already a wealth of information available from neuropixels that has only been analyzed with layer distinctions in a very cursory way. However,  layer information is in many ways poorly defined in these recordings, and is still not enough to get a putative cell type “leaf” - you are stuck at one of the branches where multiple specific types are still possible. We believe that this level of specificity is important, and that additional information will be valuable to generalize in-vivo cell type labelling strategies to other brain areas that may not be as accessible or laminar as visual cortex. 

Moving beyond optical methods
It is worth mentioning that optical recording methods (i.e. 2 photon calcium imaging) is more easily amenable to in-vivo cell type labelling because it is easier to register tissue to post-hoc histology, and because accurate morphology information is more easily acquired in-vivo. Other groups are certainly working on this (Allen institute, personal communcation, likely many others, others may have already done it actually should search). 

EM datasets can be used to generate cell type labels with varying specificity depending on the size of the volume, and these will likely improve as inference by comparing to larger EM datasets becomes possible. EM is often preceded by functional optical imaging as well. However for the reasons mentioned in the background and significance portion of this grant, we believe that it is worthwhile to pursue in-vivo cell type labelling for extracellular electrophysiology. And to our knowledge no one has successfully registered units from a neuropixels recording to an imaging tissue volume of any kind. 

Furthermore, the other information that we propose to use for in-vivo cell type labeling in specific aim 2 (spike timing relationships, extracellular waveform, optogenetically induced spiking) cannot be accessed using current optical techniques. These factors may well prove to be more effective at separating cell types without post-hoc histology than what is available in large scale optical recordings.

Conclusion
In conclusion, we believe that in-vivo cell type labeling for extracellular recordings has not been achieved with sufficient specificity, and that succeeding in our aims would enable functional circuit analyses that were previously completely impossible. Better yet, it is possible that specific aim 2 will allow us to repurpose already collected datasets for new analyses, greatly decreasing the number of experimenter hours and animal lives necessary for new discoveries. 

(C) Research Plan

Specific Aim 1 Research Plan
To assess the functional interactions between 10 (arbitrary number greater than 3) or more putative subtypes in mouse primary visual cortex during visual stimulation.

Rationale for Aim 1
We need to detangle the jungle of cell types
Attempts to investigate functional relationships in visual cortex in unsupervised ways have been unsatisfying, identifying with confidence only 3 functional subgroups - A subpopulation of neurons that seem to drive activity, neurons whose activity lags the driving population and a low-activity subpopulation that is not readily involved in the network (1). This is in clear opposition to the highly complex recurrent circuitry that we know to be present in visual cortex, and  qualitative observation of the functional connectivity matrix reveals that there does seem to be additional substructure. Being able to identify sub populations in a supervised way (i.e. with putative cell types) will elicit what substructure might represent meaningful “network roles” in the brain. 

Transcriptomics is the most well established method to identify highly specific cell types, so we believe it makes sense to begin by attempting to collect this data for in-vivo electrophysiology data since we can be confident that it will map to ground truth with reasonable confidence. 

Experimental Approach for Aim 1
There are three primary obstacles to accomplishing this goal - 1. Slicing out a volume of tissue surrounding the recording site in an appropriate way for further interrogation and 2. generating cell type labels for all cells in that volume 3. being able to register previously recorded ecephys data to the spatial volume.

Slicing out a neuropixels tract
While it will likely take some effort to get this right, we are confident that this can be accomplished consistently. Far smaller volumes of interest are trimmed successfully for EM imaging. They normally follow a pipeline that goes something like this - marking the boundaries, coarse trimming followed by fine trimming until the volume is satisfactory. We believe we can follow a similar pipeline. The neuropixels probe tract can easily be marked with florescent dye to guide course slicing. If necessary we can add additional fiducials by burning the tissue using a 2 photon microscope post mortem. We can also attempt to calibrate the dye diffusion relative to the time of perfusion so that we know exactly how close we are to the tract when we begin to see Dye. We don’t need a particularly thin slice for our proposed cell type labeling, so as long as the tissue is mounted at an appropriate angle we should be able to easily capture the tract in a ~250um volume. 

Detailed cell type labels for an entire volume
There are many promising ways to approach this problem. Others are pursuing mFISH methods to be able to identify cell types in cleared tissue. We propose a simpler method. The slice can be visualized under a patch physiology rig, then each soma near the probe tract can be sucked up using a large tipped pipet for subsequent transcriptomic profiling (personal communication, Travis Have, allen institute). While this may be a bit onerous, it is certainly possible, and we believe we should be able to use our registration technique (immediately below) to identify which Somas need to be isolated. 

Registration of ecephys data to imaging volume
While non-trivial, this has been done in other labs with various different recording arrays, ranging from tetrodes MEAs in slice. (2, 3, 4, 5). It is necessary to have sufficient sampling of the extracellular space, to know the relative position of the electodes and then to solve the solve the inverse problem of estimating the location and the size of the equivalent dipole model of the spike generator. Neuropixels probes have a high site density and uniform, known site layout in addition to a high SNR which should make this far more accurate than attempts using tetrodes. 

Once we have relative somatic positions for all neurons recorded on the probe, we can use commonly used volume registration techniques to find the best match to each unit in the labeled volume. Because we can identify the PV cell class using the fast spiking waveform, this can also be used to assist in the alignment - first aligning PV cells in the two volumes and then warping to find the best match for the others. 

Expected Results, interpretation potential pitfalls and alternative approaches for Aim 2
None ;) Jk, I just ran out of time and space. To some extent alternatives are addressed in text

Specific Aim 2 Research Plan
To determine whether better cell type resolution can be obtained for in-vivo recordings without relying on post mortem histological techniques.

Rationale for Aim 2
It has already been established that cell types can be identified to varying degrees of specificity using different modalities (transcriptomics, morphology and electrical properties )(6). The idea behind aim 2 is that different transcriptomic profiles are going to lead to differences in many aspects of the cell that can be measured. We propose that there are already many features accessible in in-vivo electrophysiology that may differ from cell type to cell type and can be used to distinguish cell types with more specificity than we have currently, without relying on additional histology techniques. 

It is possible that some transcriptomic types do not reflect real functional divisions in the circuit roles of neurons in-vivo. 46 types have good correspondence between other modalities and transcriptomis (6), so we take this to be upper bound for success of our cell type labeling. One thing to note is that since we are recording using laminar probes, we already have detailed information about the layer of the recorded unit. So we do not have to distinguish classify a unit from all 46 possibilities, but only need to distinguish between the 8-10 possibilities in a given layer which makes this problem much more tractable. 

Experimental Approach for Aim 2
We posit that there are four accessible feature sets that may be able to distinguish different cell types - detailed spatio-temporal information of the extracellular waveform, spike timing relationships, functional properties, and lastly detailed analysis of optogenetically induced spiking. Some of these are inherently available in all neuropixels recordings (waveform and spike timing). For these we propose additional analysis methods that will render them more useful than currently available data. Others will require specific experimental conditions and stimuli (optogenetics and functional properties) that we will use during our recordings, described below. 

Spatiotemporal waveform
The waveform is aThe extracellular waveform is already commonly used to classify units into broad spiking and narrow spiking subclasses, and recently a new classification method WAVEmap was able to find 9 distinct subclasses of extracellular waveforms in primates (8)(peak channel only). However, recent attempts to use the extracellular waveform to distinguish subgroups of neurons in an unsupervised way only found 3 subgroups (7). We propose that a number of analytical methods could improve the utility of this feature set. 
Reverse filtering the waveform is necessary to correct phase offsets introduced by the hardware 
Interpolation in time and space to account for motion and slight timing offsets
Using not only the mean waveform but assessing variability of the waveform and possible systematic changes (ie if waveform changes shape for the second spike in a burst)
Using the waveform and the inferred dipole from Aim 1 to actually estimate probabilities of possible morphology details using the full 3d spatiotemporal waveform (instead of 1 channel or 2d as in the previous papers cited above)
And of course comparing only across the same layer may reveal previously obscured distinctions. 

Spike timing relationships
Spike timing relationships are also commonly used to classify units into subclasses, this time called fast spiking (which corresponds to the narrow spiking waveform) and regular spiking. Furthermore, including autocorrelation information in the WAVEmap classification improves discriminability of clusters (personal communication, Eric Lee). It is also possible that there is even more information in the second and third order spiking relationships that has not been assessed (bustiness, firing rate variability). Lastly, spike-field coherence can be computed from neuropixels recordings may vary between cell types. 

Functional properties
Many experiments have shown that different cell types have different functional responses (one example is that VIP cells respond differently to novel and familiar images- preliminary data). However the trick here will be to find functional properties in a way that will be easily generalizable. It is possible that response to natural images will help distinguish subtypes, but it is not clear what the corresponding condition would be for the prefrontal cortex or amygdala. We would like to avoid the scenario where researchers in different brain areas or species have to find their own stimulus set. Thus we propose to record in 5 functional states that may reasonably generalize to other brain ares - 1. Awake, in darkness (spontaneous condition 1) 2. Awake, with grey screen (spontaneous condition 2) 3. Awake with visual stimulation (engaged) 4. Anesthetized (unconscious). We will assess changes in firing properties or network involvement in these states. 

Optogenetically induced spiking
We will induce spikes in recorded neurons using channel rhodopsin stimulation to see if the induced spikes vary in a systematic way from cell type to cell type that can be distinguished from variability in expression. Specifically we would hope to recreate some of the features in the Allen institute E type classification, like time to first spike and changes in height between first and second spike. This approach would first be used in slice with patch recordings to assess feasibility before attempting to recreate the conditions in-vivo.

Expected Results, interpretation, potential pitfalls and alternative approaches for Aim 2
None again. Whoopsies!


References 
Jia, X., Siegle, J., Billeh, Y., Durand, S., Heller, G., Ramirez, T., Arkhipov, A., & Olsen, S. (2019). Subnetworks mediating feedforward and feedback processes revealed by multi-area Neuropixels recordings. https://doi.org/10.32470/ccn.2019.1281-0

Lee, C. W., Szymanska, A. A., Ikegaya, Y., & Nenadic, Z. (2013). The accuracy and precision of signal source localization with tetrodes. Proceedings of the Annual International Conference of the IEEE Engineering in Medicine and Biology Society, EMBS. https://doi.org/10.1109/EMBC.2013.6609554

Lee, C. W., Dang, H., & Nenadic, Z. (2007). An efficient algorithm for current source localization with tetrodes. Annual International Conference of the IEEE Engineering in Medicine and Biology - Proceedings. https://doi.org/10.1109/IEMBS.2007.4352531

Weir, K., Blanquie, O., Kilb, W., Luhmann, H. J., & Sinning, A. (2015). Comparison of spike parameters from optically identified GABAergic and glutamatergic neurons in sparse cortical cultures. Frontiers in Cellular Neuroscience, 8(JAN). https://doi.org/10.3389/fncel.2014.00460

Mechler, F., Victor, J. D., Ohiorhenuan, I., Schmid, A. M., & Hu, Q. (2011). Three-dimensional localization of neurons in cortical tetrode recordings. Journal of Neurophysiology, 106(2). https://doi.org/10.1152/jn.00515.2010

Gouwens, N. W., Sorensen, S. A., Berg, J., Lee, C., Jarsky, T., Ting, J., Sunkin, S. M., Feng, D., Anastassiou, C., Barkan, E., Bickley, K., Blesie, N., Braun, T., Brouner, K., Budzillo, A., Caldejon, S., Casper, T., Casteli, D., Chong, P., … Koch, C. (2018). Classification of electrophysiological and morphological types in mouse visual cortex. BioRxiv. https://doi.org/10.1101/368456

Jia, X., Siegle, J. H., Bennett, C., Gale, S. D., Denman, D. J., Koch, C., & Olsen, S. R. (2019). High-density extracellular probes reveal dendritic backpropagation and facilitate neuron classification. Journal of Neurophysiology, 121(5). https://doi.org/10.1152/jn.00680.2018

Lee, E. K., Balasubramanian, H., Tsolias, A., Anakwe, S., Medalla, M., Shenoy, K. v., & Chandrasekaran, C. (2021). Non-linear dimensionality reduction on extracellular waveforms reveals cell type diversity in premotor cortex. ELife, 10. https://doi.org/10.7554/eLife.67490

Spix, T. A., Nanivadekar, S., Toong, N., Kaplow, I. M., Isett, B. R., Goksen, Y., Pfenning, A. R., & Gittis, A. H. (2021). Population-specific neuromodulation prolongs therapeutic benefits of deep brain stimulation. Science, 374(6564). https://doi.org/10.1126/science.abi7852
