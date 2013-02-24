## Contents

-   [Introduction](#Introduction)
-   [Quick Tutorial](#Quick_Tutorial)
-   -   [Single variant test](#Single_variant_test)
    -   [Group test](#Group_test)
    -   [Options in association tests](#Options_in_association_tests)
    -   [Phenotype file](#Phenotype_file)
    -   [Covariate file](#Covariate_file)
    -   [Use gene/set based rare-variant tests](#Use_gene.2Fset_based_rare-variant_tests)

-   [Contact](#Contact)


* * * * *

# Introduction

R(are) V(ariant) tests is a flexible software aimed to help
association tests.

# Quick Tutorial

We will show how to use *rvtests* software in typical use cases.

## Single variant test

    rvtests --inVcf input.vcf --pheno phenotype.ped --out output --single wald,score

Use Wald and Score test statistics in single variant association
tests to test every variant.

## Group test

Rvtests supports large range of tests

-   single (--single): score, wald, exact
-   burden (--burden): cmc, zeggini, mb, exactCMC, rarecover, cmat
-   variable threshold (--vt): price, cmc
-   kernel method (--kernel): skat, KBAC
-   meta analysis method (--meta): : score, cov

You can flexibly specify testing units. To test by gene, use
--geneFile to specify the gene range. Optionally, use --gene to
specify which gene to test:

    rvtests --inVcf input.vcf --pheno phenotype.ped --out output --geneFile refFlat_hg19_uniq_gene.txt.gz --burden cmc --vt price --kernel skat,kbac

Rvtests will use CMC method, variable threshold method(proposed by
Price) and kernel based method (SKAT by Shawn Lee and KBAC by
Dajiang Liu) to test every gene listed in
*refFlat\_hg19\_uniq\_gene.txt.gz*.

You can also test by set using --setFile and --set.

## Options in association tests

Rare variants tests usually choose different frequency cutoffs.
Frequency Cutoff

                 --freqUpper : Specify upper frequency bound to be included in analysis
                 --freqLower : Specify lower frequency bound to be included in analysis

People Filter

           --peopleIncludeID : give IDs of people that will be included in study
         --peopleIncludeFile : from given file, set IDs of people that will be included in study
           --peopleExcludeID : give IDs of people that will be included in study
         --peopleExcludeFile : from given file, set IDs of people that will be included in study

Site Filter

                 --rangeList : Specify some ranges to use, please use chr:begin-end format.
                 --rangeFile : Specify the file containing ranges, please use chr:begin-end format.
                  --siteFile : Specify the file containing sites to include, please use "chr pos" format.
              --siteDepthMin : Specify minimum depth(inclusive) to be incluced in analysis
              --siteDepthMax : Specify maximum depth(inclusive) to be incluced in analysis
                --siteMACMin : Specify minimum Minor Allele Count(inclusive) to be incluced in analysis
                  --annoType : Specify annotation type that is follwed by ANNO= in the VCF INFO field, regular expression is allowed

Genotype Filter

              --indvDepthMin : Specify minimum depth(inclusive) of a sample to be incluced in analysis
              --indvDepthMax : Specify maximum depth(inclusive) of a sample to be incluced in analysis
               --indvQualMin : Specify minimum depth(inclusive) of a sample to be incluced in analysis
    

## Phenotype file

## Covariate file

## Use gene/set based rare-variant tests

# Contact

Questions and requests can be sent to Xiaowei Zhan
([zhanxw@umich.edu](mailto:zhanxw@umich.edu "mailto:zhanxw@umich.edu"))
or Goncalo Abecasis
([goncalo@umich.edu](mailto:goncalo@umich.edu "mailto:goncalo@umich.edu"))

Rvtests is a collaborative effort by Youna Hu, Bingshan Li, Dajiang
Liu.


