### Author: Boris Alladassi
### Date: Oct 19th, 2019
### Comments and suggestions
---
#### Comments
Overall, good job! I like how you did a very thorough data inspection. You also did well by describing each chunk of code as it makes it easy to follow through.

#### Suggestions

I would suggest you combine lines of codes together by using pipe `%>%`

It is a good habit to sort before merging although unlike UNIX, R does not require that.

You may want to leverage the ease of function `select()` of `dplyr` to create the data frame **join_start**. Below is a suggestion:

```join_start <- sorted_snp %>% select(SNP_ID, Chromosome, Position)```
The instructions of the assignment do not require us to create files for **"unknown"** and **"multiple"** position this time.

You did create multiple intermediate files. In total, there were 83 files in the global environment. In R, this can be memory intensive especially with large files. You could delete useless files as you move on or give the same name to intermediate files or even better, use pipe.

It would be better to have more explicit names for your files like **maize_Chromosome_unknwon** instead of **m_Chrom_Unknown**.

On the same note, why not create separate directories for maize and teosinte with their respective files.

To be memory efficient, you could use function ```arrange()``` to sort the data frame right after filtering in your for loop (code line 174) as shown below:

```d.frame <- filter(join_maize1, Chromosome == i) %>% arrange(., as.numeric(Position))``` 

#### Part III
With a dot Plot, the total number of SNPs is not obvious. I suggest a bargraph that shows directly the actual number on the y-axis.


#### Additional notes
Check again, it seems your HTML file is not the same as your Rmarkdown file. You may want to update it.

Add a description of the content of this repository to your **README.md** file.

Using `as.numeric()` will help to sort as numbers.
