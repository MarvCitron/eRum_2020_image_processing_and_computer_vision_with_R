# [eRum 2020] Image processing and computer vision with R

This is a repository for purposes of a workshop _Image processing and computer vision with R_
at [eRum 2020](https://2020.erum.io/).

---

## Abstract

Although R is sometimes not considered as a number-one language for image processing, there are options for effectively handling these tasks in the R environment. Furthermore, a large R speaking community would like to combine image data analysis with other kinds of analyses by keeping all their code "under one roof" within R.

In this workshop, we will revisit available packages such as magick, imager, EBImage (and some others) written purely in R (and for R), which deal mainly with image processing. A couple of times will be dedicated to amazing Bnosac’s family of R packages enabling computer vision and some other algorithmic tasks, besides other, objects or face detection and recognition. We will also take a short look a bit deeper into state-of-the-art possibilities bridging the R environment to non-R-based libraries using API packages, namely employing of dlib R package.

---

## How to prepare yourself before the workshop

To make things even smoother, it would be great when you install the following R packages before the beginning of the workshop. We are using lots of packages we are neither authors nor maintainers of, so all the credits go to their original authors!

- The following packages,

`bmp`, `jpeg`, `png`, `magick`, `tesseract`, `imager`, `OpenImageR`, `BiocManager`, `dlib`, `devtools`, `remotes`,

could be installed one by one in RStudio or using the code below,

```
invisible(
    
    lapply(
        
        c(  
            "bmp",
            "jpeg",
            "png",
            "magick",
            "tesseract",
            "imager",
            "OpenImageR",
            "BiocManager",
            "dlib",
            "devtools",
            "remotes"
        ),
        function(my_package){
            
            if(
                !(
                    my_package %in% rownames(installed.packages())
                )
            ){
                
                install.packages(
                    my_package,
                    dependencies = TRUE,
                    repos = "http://cran.us.r-project.org"
                )
                
            }
            
        }
        
    )
    
)
```


- The package "EBImage" is stored on Bioconductor rather than CRAN, so we need to install it following a kinda different code,

```
BiocManager::install("EBImage")
```


- The Bnosac's family of R packages for computer vision requires Rtools, devtools, and should be installed from GitHub.
  * Firstly, if you haven't installed Rtools yet, click on
  [https://cran.r-project.org/bin/windows/Rtools/](https://cran.r-project.org/bin/windows/Rtools/)
  and please download the installer based on your operation system version.
  * Then, if you haven't customized your config file `.Renviron` yet, copy and run the following command in R console

```
writeLines('PATH="${RTOOLS40_HOME}\\usr\\bin;${PATH}"', con = "~/.Renviron")
```

to set the correct paths to the Rtools.

* Finally, install devtools using

```
install.packages("devtools")
```

- Then, take a sip of coffee or rather two while you are installing Bnosac's packages using

```
devtools::install_github(
    "bnosac/image",
    subdir = "image.dlib",
    build_vignettes = TRUE
)

devtools::install_github(
    "bnosac/image",
    subdir = "image.darknet",
    build_vignettes = TRUE
)

devtools::install_github(
    "bnosac/image",
    subdir = "image.libfacedetection",
    build_vignettes = TRUE
)
```

- Once you are done with that, please download the files containing weights for some deep neural networks
## 
##  https://drive.google.com/drive/folders/1qNKJwmANHFJs-yAXdSQXz_Bc-tGsV6SY?usp=sharing
## 
##         and
## 
##   https://drive.google.com/drive/folders/1qNKJwmANHFJs-yAXdSQXz_Bc-tGsV6SY?usp=sharing
## 
##         somewhere to your local drive (details and proper paths to
##         the files with weight will be provided during the workshop).

Please see the attached code for details. You are also emphasized to download the folder with files containing weights for some deep neural networks somewhere to your local drive (information about proper paths to the files with weight will be provided during the workshop),

https://drive.google.com/drive/folders/1qNKJwmANHFJs-yAXdSQXz_Bc-tGsV6SY?usp=sharing

and

https://drive.google.com/drive/folders/1qNKJwmANHFJs-yAXdSQXz_Bc-tGsV6SY?usp=sharing.

We have checked the Bnosac's packages work appropriately on Windows computers. Linux systems are also recommended. We can't guarantee they will perform well on Macs.


---

## Tutors

Lubomir Stepanek, MSc., M.D. is an assistant lecturer at the Department of Biomedical Statistics, Institute of Biophysics and Informatics, First Faculty of Medicine, Charles University, and tries to finish his Ph.D. somewhere around. He is absorbed by applied biostatistics, psychometrics, facial image processing, and computer vision.

Jiri Novak, MSc. is a teaching assistant and a Ph.D. student at the Department of Economic Statistics, Faculty of Informatics and Statistics, University of Economics. He is interested in Statistical Disclosure Control and R programming.



