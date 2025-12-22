# Entorn virtual amb conda

## Crear un nou entorn virtual utilitzant conda

Per crear un entorn virtual amb conda, executa la següent comanda al directori arrel del projecte:

```sh
conda env create --prefix=./.conda --file=environment.yml
```

Per assegurar-te que l'entorn virtual s'ha creat correctament, pots comprovar que el directori `.conda/` s'ha creat al directori arrel del projecte.

> [!NOTE]
> Si no vols utilitzar el fitxer `environment.yml`, pots crear l'entorn virtual amb les següents comandes:

```sh
conda create --prefix=./.conda
conda activate ./.conda
conda install r-base=4.5.2 r-ggplot2 r-fitdistrplus r-kableExtra r-knitr \
    r-languageserver r-MASS r-rmarkdown r-survival r-ggstatsplot r-svglite \
    r-tidyverse
```

> [!TIP]
> Miniconda requereix menys espai i és més lleuger que Anaconda. Per instal·lar Miniconda en sistemes macOS, pots utilitzar Homebrew:

```sh
brew install --cask miniconda
conda init
conda config --set auto_activate_base False
source ~/.bash_profile
conda tos accept --override-channels --channel https://repo.anaconda.com/pkgs/main
conda tos accept --override-channels --channel https://repo.anaconda.com/pkgs/r
```

## Activar i desactivar l'entorn virtual amb conda

Per activar l'entorn virtual, executa la següent comanda:

```sh
conda activate ./.conda
```

Per desactivar l'entorn virtual, executa la següent comanda:

```sh
conda deactivate
```

> [!TIP]
> Per canviar el missatge de l'entorn virtual perquè mostri el nom de l'entorn un cop activat, pots executar la següent comanda per escurçar-lo:

```sh
conda config --set env_prompt '({name}) '
```

## Codis de Països (ISO 3166)

<https://www.kaggle.com/datasets/wbdill/country-codes-iso-3166>

## Estructura del Projecte

```plaintext
/
├── .editorconfig            # Configuració d'editor per a consistència de codi
├── .gitignore               # Fitxer per excloure arxius del control de versions
├── README.md                # Documentació general quant al projecte
├── LICENSE                  # Fitxer de la llicència
├── .vscode/
│   ├── settings.json        # Configuració de l'espai de treball
│   └── extensions.json      # Extensions recomanades de VS Code
├── data/
│   └── hotel_bookings.csv   # Dataset amb les dades dels dos hotels
├── environment.yml          # Dependències per crear un entorn virtual amb conda
├── hotel_bookings.Rmd       # Fitxer amb l'anàlisi estadística descriptiva
└── hotel_bookings.test.Rmd  # Fitxer per fer proves amb el dataset
```
