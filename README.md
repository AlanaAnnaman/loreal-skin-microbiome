# What is Living on Your Face? A Skin Microbiome Analysis

## The Big Question
Human skin is covered in billions of bacteria. But what kind? And how many? 

To find out, I analyzed real DNA sequencing data from a human cheek swab. My goal was to take raw, messy data straight from a DNA sequencer and figure out exactly which bacteria were living on that person's skin.

## Where the Data Came From
I used public data from **L'Oral Study 12**, a real scientific study looking at skin microbiomes. 
* **The Data:** [NCBI SRA Accession ERR12408454](https://www.ncbi.nlm.nih.gov/sra/ERX11784472)
* **The Science Paper:** [A multi-study analysis enables identification of potential microbial features associated with skin aging signs (Frontiers in Aging, 2024)](https://doi.org/10.3389/fragi.2023.1304705)

## How I Did It (The Pipeline)
I wrote a bioinformatics pipeline to clean and analyze the DNA. Here is what it did:

1. **Quality Control (The Cleanup):** I started with 18,036 raw DNA reads. DNA sequencers make mistakes, so I used a tool called **QIIME2** and **DADA2** to filter out the junk. I kept 89.4% of the data (16,121 clean reads).
2. **Grouping (Finding the Species):** I grouped identical DNA sequences together. This gave me **23 unique types of bacteria**.
3. **Naming (The Detective Work):** I compared my 23 sequences against a massive database of known bacteria (using a method called **VSEARCH**). 

## The Results: Who is There?
Out of the 23 bacteria found, **one single species completely took over.**

*  **The Dominant Bacterium:** *Cutibacterium acnes*. This one bacterium made up **82% of the entire sample** (13,222 reads). It is a normal, healthy bacterium that lives in your skin's oil glands.
*  **The Supporting Cast:** The rest of the sample was a mix of common skin bacteria (*Staphylococcus*, *Corynebacterium*) and mouth bacteria (*Streptococcus*) that likely washed onto the cheek from saliva.

## Why This Matters
Unlike your gut, which has hundreds of different bacteria living together, your skin is a harsh environment. It is usually dominated by just a few tough species. This analysis perfectly matches what scientists know about the human skin microbiome.

## How to View the Results
You can explore the raw results by downloading the `.qzv` files in the `results/` folder and dragging them into [https://view.qiime2.org](https://view.qiime2.org). 
* `taxonomy.qzv` shows the names of the bacteria.
* `table.qzv` shows the exact DNA counts.

## Built With
* QIIME2
* DADA2
* SILVA Database
* VSEARCH

## Author
Alana Annamanthadoo
[LinkedIn](https://linkedin.com/in/alana-annaman) | [GitHub](https://github.com/AlanaAnnaman)
