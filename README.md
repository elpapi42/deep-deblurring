# Deep Deblurring
An open-source personal-project application that offers an image deblurring/restoration solution powered by the latests Deep Learning advances in Image Restoration Research. The service expose an powerful Deep Learning Model specialized in Image Quality Restoration called DeblurGAN-V2 (Orest Kupyn and Team "[DeblurGAN-v2: Deblurring (Orders-of-Magnitude) Faster and Better](https://arxiv.org/abs/1908.03826)").

The architecture of this service is composed by a few modules: a Vue.js Frontend application that cosumes a Flask Backend API, this API orchestrate the relationships with the data recollection strategy (For model retraining/finetunning) and communicates with a private Tensorflow Serving API that exposes the core application feature, the Deep Learning DeblurGAN-V2 Model.

![Image](https://github.com/ElPapi42/deep-deblurring/blob/master/system_architecture.png "Arch")

Due to huge budget limitations, few specifical strategies was adopted for the training and deployment stacks:

1. For the training of the model architecture, we use Google Colab, a free Jupyter Notebooks GPU-Enabled enviroments, ideal for training and experimentation, our [Notebook](https://github.com/ElPapi42/deep-deblurring-model/blob/master/deblurrer/colab/TrainBook.ipynb) implements an integrated deployment logic that allows researchers to deploy models to production with few clicks, basically commiting a new version model to [Serving](https://github.com/ElPapi42/deep-deblurring-serving) repo. This serving repo is automatically deployed to Heroku.
2. Talking about Heroku, and keeping in the lines of the low budget limitations, we deploy all the software modules that compose Deep Deblurring on this platform, sucking the max out of its free tier, anyways, the time limitations push us to setup strict usage limits for the Backend API.
3. Heroku does not offer flexible enough static storage solution on its free tier, so we integrate [Cloudinary](https://cloudinary.com/) to the backend as Static Host Provider, the free tier of this platform is generous enough for our use case.

If you wish to know details about the implementation of each specific service that compose Deep Deblurring architecture, visit their respective dedicated repository:

* Frontend: https://github.com/ElPapi42/deep-deblurring-frontend
* Backend: https://github.com/ElPapi42/deep-deblurring-backend
* Serving: https://github.com/ElPapi42/deep-deblurring-serving
* Model: https://github.com/ElPapi42/deep-deblurring-model

PD: The final porpoise of this Project is to have a great item for show to potential employers, im currently actively looking for job, so, if you feel my skills match your needs, touch me on [LinkedIn](https://www.linkedin.com/in/whitmanbohorquez/) or via email: whitman-2@hotmail.com, we surely can talk!

