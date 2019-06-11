# TODO


big picture keras:

- [ ] how to specify to use A SPECIFIC METRIC as the objective function?
- [ ] how to record/report confusion matrix? roc curve? roc auc?
    - how roc auc and accuracy and precision are related...
    - cannot just look at one in isolation, need whole context


ray tune notebook:

- [ ] run on CoLab
- [ ] figure out how we're going to plot and analyze results
    - combine previously-written functions for plotting etc
    - pass it data/information from the auto-loaded dataframe
- [ ] save results to a directory and visualizing with tensorborad
    - how to save files and transfer them OUT with the tools we have?
    - using command line google drive access/api sign-in?
    - CONNECT TO A LOCAL JUPYTER RUNTIME



data exploration notebook:

- [x] where did all the transforms go?
    - moved to each individual transform's notebook


keras 1d cnn notebook: 

- [x] fix junD and chromosome numbering wording.
- [x] replace confusion matrix plot with ones from powerx and quantilex.
- [x] explicitly call out what the y_model looks like
- [x] explicitly call out that we round to determine the final prediction
- [x] remove any class weights versus sample weights
- [x] the way that we assemble the chromatin model is a little bit confusing.
    - prepare a little description of what we're doing and why we say
    - seq = Conv1D(...)(seq)
    - explain by saying layer2 = Conv1D(...)(layer1)
    - then say that instead we just keep chaining them together with same var.
- [x] increase batch size


keras sklearn 1d cnn notebook:

- [x] improve explanation of what we're doing - three networks
    - no chromatin
    - chromatin with sample weights
    - chromatin with class weights


log transform notebook:

- [x] standardize and scale the log transform
- [x] why did we try the power and quantile transforms in the first place?


power transform notebook:

- [x] we don't mention or show the power transform, or how the distribution of chromatin values is affected.
- [ ] we also don't mention normalization or class weighting at a thousand-foot view level. 
- [ ] add an outline or summary to the top
- [ ] use class weights, not sample weights
- [ ] if we are just making tiny modifications to a prior notebook, then say so explicitly at the top, and link to that notebook.


quantile transform notebook:

- [ ] we again don't mention or show the quantile transform, or how the distribution is changed.
- [ ] this notebook mentions "variation 3" - but where are these "variations" listed? linked?
- [ ] modify the paragraphs and sections to mention what is specific to the quantile transform.
- [ ] if we are just making tiny modifications to a prior notebook, then say so explicitly at the top, and link to that notebook.
- [ ] use class weights, not sample weights







