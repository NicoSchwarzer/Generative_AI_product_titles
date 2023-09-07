# Generative_AI_product_titles

This repo contains the code for my master thesis on SOTA generative language models for AirBnB listing title generation.¬ I focus on listings in London and data is provided from Inside AirBnB.
Specifically, I use the listing description as the feature to condition the title generation on.

Firstly, I fine-tune pre-trained Transformer, i.e. DistilBART, BART (1) and PEGASUS (2). I also make use of LLaMa (3) (by META AI) combined with parameter-efficient fine-tuning (PEFT) mechanisms, namely LoRA (4) and LLaMa-Adapters (5). The training set is compromised of high-quality listings. I use the implementation provided by Lightning AI (6).

To test if machine-generated titles are more attractive, two evaluation approaches are deployed. Firstly, I train a multi-modal discriminator which maps from the title and many confoudners (from modalities text, images and tabular data) to the the difference in reviews across nine months (a proxy to occupancy) - see th figure below. This allows for the calculation of counterfactual occupancies – under the assumption of different listing names

<p align="center">
<img src="https://github.com/NicoSchwarzer/Generative_AI_product_titles/blob/main/3_discriminator_counterfactuals/mm_design.PNG" width="425" height="200">
</p>


I also conducted a survey in which respondents could pick a preferred title amongst four alternatives. A deep learning model could learn the relationship between titles and associated descriptions and their perceived attractiveness - as is displayed below.

<p align="center">
<img src="https://github.com/NicoSchwarzer/Generative_AI_product_titles/blob/main/4_survey/discriminator_2.PNG" width="425" height="170">
</p>


This REPO contains all code for this project as well as code for you to easily use the models to generate further titles.

## Working with my code

To replicate all steps, you merely need a few dataframes, which I can provide. Note that as I used Google drive as the storage option, I read in all files form there. 
To leverage my models to easily generate titles, consider the files in the folder *5_Generate_your_own_titles*. Once you have requested the models from me, you can easily run the functions attached to generate titles for given descriptions based on a model of your choice. Importantly, note that the 'Replication_Title_generation_with_tuned_LLaMa_models.ipynb' notebook uses the LLaMa-1 generation as LLaMa-2 requires a permit by META AI.


## Structure of the code 

As stated above, the first four folders contain all code I wrote for this project. Here is some information on the files in the corresponding folders.

## *1_data_retrieval*
This folder contains files used for data retrieval, including scraping the listings main images. 

## *2_title_generation*
This folder contains two subfolders. 

The first one, *summarization_transformers* contains the files used for finetuning pre-trained (Distil)BART & PEGASUS models.

The second one, *LLaMa_tuning * contains the files used for PEFT-based LLaMa optimization for both generations of LLaMa. It also contains files used to generate titlrs using non-optimized LLaMa models and a file used to fine-tuned LLaMa on all listings.

## *3_discriminator_counterfactuals*
This folder contains files to finetune an SBERT model using Masked Language Modelling and Negative Multiple Ranking using the AirBnB data. This model is used to embed the description and the titles.
Also, a file is used to create further variables as inputs to the discriminator model. 
Further files are used for discriminator training and counterfactual calculation.

## *4_survey*
This folder contains files used to set up thumbnails shown on the survey and further metadata needed for setting up a survey using *Unipark*. Also, a file analyzing survey results and a file used for training the model based on these can be found here.

## *5_Generate_your_own_titles*
See above :)

## Contact me
Feel free to contact me for access to data and models - on in case of questions: nico.schwarzer97@gmail.com




**References**

(1) Lewis, M., Liu, Y., Goyal, N., Ghazvininejad, M., Mohamed, A., Levy, O., & Zettlemoyer, L. (2019). Bart: Denoising sequence-to-sequence pre-training for natural language generation, translation, and comprehension. arXiv preprint arXiv:1910.13461.

(2) Zhang, J., Zhao, Y., Saleh, M., & Liu, P. J. (2020). Pegasus: Pre-training with extracted gap-sentences for abstractive summarization. In International Conference on Machine Learning, 11328–11339.

(3) Touvron, H., Lavril, T., Izacard, G., Martinet, X., Lachaux, M. A., Lacroix, T., & Lample, G. (2023). Llama: Open and efficient foundation language models. arXiv preprint arXiv:2302.13971 

(4) Hu, E. J., Shen, Y., Wallis, P., Allen-Zhu, Z., Li, Y., Wang, S., & Chen, W. (2021). Lora: Low-rank adaptation of large language models. arXiv preprint arXiv:2106.09685 .

(5) Zhang, R., Han, J., Zhou, A., Hu, X., Yan, S., Lu, P., & Qiao, Y. (2023). Llama-adapter: Efficient fine-tuning of language models with zero-init attention. arXiv preprint arXiv:2303.16199.

(6) Lightning-AI (2023, May). Lit-llama release. Retrieved from https://github.com/Lightning-AI/lit-llama




- contact me for models and questions

