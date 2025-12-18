# Virtual environment with conda

## Create new virtual environment using conda

To create a virtual environment with conda, run the following command in the
project root directory:

```sh
conda env create --prefix=./.conda --file=environment.yml
```

To ensure that the virtual environment has been created correctly, you can check
that the  `.conda/` directory has been created in the project root directory.

> [!NOTE]
> If you do not want to use the `environment.yml` file, you can create the
> virtual environment with the following commands:

```sh
conda create --prefix=./.conda
conda activate ./.conda
conda install r-base=4.5.2 r-ggplot2 r-fitdistrplus r-kableExtra r-knitr \
    r-languageserver r-MASS r-rmarkdown r-survival r-ggstatsplot r-svglite \
    r-tidyverse
```

> [!TIP]
> Miniconda requires less space and is lighter than Anaconda. To install
> Miniconda on macOS systems, you can use Homebrew:

```sh
brew install --cask miniconda
conda init
conda config --set auto_activate_base False
source ~/.bash_profile
conda tos accept --override-channels --channel https://repo.anaconda.com/pkgs/main
conda tos accept --override-channels --channel https://repo.anaconda.com/pkgs/r
```

## Activate and deactivate the virtual environment with conda

To activate the virtual environment, run the following command:

```sh
conda activate ./.conda
```

To deactivate the virtual environment, run the following command:

```sh
conda deactivate
```

> [!TIP]
> To change the virtual environment prompt so that it shows the environment
> name once activated, you can run the following command to shorten it:

```sh
conda config --set env_prompt '({name}) '
```

## Country Codes (ISO 3166)

<https://www.kaggle.com/datasets/wbdill/country-codes-iso-3166>
