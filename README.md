# sandbox

Click [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/clement-lee/sandbox/main?urlpath=rstudio). This will open a new page with RStudio in a virtual environment (VE). If not, a page with binder at the top will open. Click **launch** and wait for the VE to be built (this may take a few minutes).

Within the VE, you can run scripts as you would on a local machine, or upload your Rmarkdown file and knit it to the desired output (pdf, html, etc.) If the output is successfully knitted, it means that you have *in principle* achieved reproducibility. If it cannot be knitted **but it worked on your local machine**, the first thing to check is if there are absolute paths ([explanation](https://www.redhat.com/sysadmin/linux-path-absolute-relative)) in your script. Change them to relative paths, and knitting should work again.

Even if knitting an Rmd file works, there are several commands that you need to ensure are not in it:

1. `install.packages()`: when someone else tries to reproduce your output, you don't want this command to mess up their machine.
2. `View()`: this is a command most suitable for interactive analysis i.e. you type in the console and results appear. Rmarkdown is designed for non-interactive output generation, so you should not include any `View()` in an Rmd file.
3. `setwd()`: The issue with this command is related to that for absolute paths. Also, this command should be used interactively, either in the console, or substituted by clicking `Session` $\rightarrow$ `Set Working Directory` in RStudio.
