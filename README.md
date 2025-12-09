
 # Importing and Running a Nextflow Workflow on Lifebit CloudOS"


# 1. Prerequisites

Before starting, ensure the following requirements are met:

- You have a **Lifebit CloudOS account** with the necessary permissions.
- Access to the relevant **GitHub repository** containing the Nextflow workflow.

---

# 2. Importing the Workflow

## 2.1 Log in to Lifebit CloudOS

Open **Lifebit CloudOS** in your browser and log in with your credentials.

```text
# No code needed; perform via browser login
````

## 2.2 Configure Batch Queues

1. Navigate to:

```

Switch Workspace -> Settings -> Batch Queues -> Nextflow

```

2. Click the **Add Batch Queue** button (top right corner) and add the following instances:

| Instance Type |
| ------------- |
| c5.2xlarge    |
| c5.9xlarge    |
| r5.24xlarge   |

3. Save the configuration as **Geneppy_all**.

## 2.3 Import Workflow from GitHub

1. Navigate to:

```
Advanced Analytics -> Import

or through Pipeline & Tools section:

Advanced Analytics -> Pipelines & Tools -> Import
```

2. Enter the repository URL and click **Import**.

```text
# Example:
# https://github.com/your-organization/your-nextflow-workflow
```

---

# 3. Configuring the Workflow

After importing the workflow:

1. Click **Parameters**.
2. Provide values for the mandatory inputs as follows:

```r
# Mandatory Workflow Parameters
chr              <- "chr1"                        # Chromosome
annotations_cadd <- "Cadd annotation database"    # CADD annotations
homos_vep        <- "VEP database"               # VEP homozygous database
plugin1          <- "gnomad.genomes.r3.0.inc"   # Plugin 1
plugin2          <- ".whole_genome_SNVs.tsv"    # Plugin 2
cadd_data        <- "Cadd data"                 # CADD data file
ethnicity        <- "ethinicity.txt"            # Ethnicity information
kary             <- "XY_karyo.txt"              # Karyotype file
vcf              <- "chr11"                      # VCF input
outDir           <- "${JOB_RESULTS_LOCATION}"    # Output directory
```

> **Note:** Replace placeholder paths and filenames with the actual dataset and files relevant to your analysis.

---

# 4. Run the Workflow

Once all parameters are set:

1. Select an existing “Project” or create a new one using “New project”.

2. Modify the default job “Name” for better future tracking of your job.

3. Click **Run Workflow**.

4. Monitor the job status on Lifebit CloudOS.

5. Retrieve outputs from the specified `outDir` upon completion.


```text
# Workflow execution is managed through the Lifebit CloudOS interface.
```

---

# References

* [Lifebit CloudOS Documentation](https://lifebit.ai/cloudos/docs)
* [Nextflow Documentation](https://www.nextflow.io/docs/latest/index.html)

```
