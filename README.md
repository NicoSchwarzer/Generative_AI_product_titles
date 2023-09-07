# Generative_AI_product_titles

This repo contains the code for my master thesis on SOTA generative language models for AirBnB listing title generation.¬ I focus on listings in London and data is provided from Inside AirBnB.
Specifically, I use the listing description as the feature to condition the title generation on.

Firstly, I fine-tune pre-trained Transformer, i.e. DistilBART, BART (1) and PEGASUS (2). I also make use of LLaMa (3) (by META AI) combined with parameter-efficient fine-tuning (PEFT) mechanisms, namely LoRA (4) and LLaMa-Adapters (5). The training set is compromised of high-quality listings.

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
To leverage my models to easily generate titles, consider the files in the folder “5_Generate_your_own_titles”. Once you have requested the models from me, you can easily run the functions attached to generate titles for given descriptions based on a model of your choice. 

## Structure of the code 







To


 
to optimize product titles using AirBnB listings as an example. Subsequently, I deploy two sophisticated methods (multi-modal deep-learning based and RLHF-inspired) to judge the quality of the generated titles. 

Drive/colab!

Cite:
Lora
LLaMa Adapter
LlaMa
Lighting Ai LLaMa
PEGASUS
BART

The code is still messy and in jupyter notebook format as it was developed on Google Colab.

Importantly, note that the 'Replication_Title_generation_with_tuned_LLaMa_models.ipynb' notebook uses the LLaMa-1 generation as LLaMa-2 requires a permit by META AI.




- contact me for models and questions

