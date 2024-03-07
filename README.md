# DLW2024
We attend Deep Learning Week 2024 hosted by MLDA@EEE Club, NTU. In this competition, our tasks is removing low-quality image-caption pairs to improve video generation models.

With the given dataset (image-caption pairs), we firstly run re-caption for all images by using different models, and collect multiple captions for each image. Because of limited hardware resources, we only can use light models, which are ViT_GPT2, BLIP, and HuggingFace_Transformer_imagetotext model. Along with the given caption from dataset, we have totally 4 captions for one image after re-captioning.

The next step is ranking and selecting captions. 4 captions would be ranked based on CLIP score (OpenAI), and only top two ranks would be selected. Besides, we run a YoLov5 to detect object in image, which gives details about which objects the captions should include.

We combining lists of objects and newly captions, and prompt GPT-4 to generate a much more synthetic and descriptive captions.
