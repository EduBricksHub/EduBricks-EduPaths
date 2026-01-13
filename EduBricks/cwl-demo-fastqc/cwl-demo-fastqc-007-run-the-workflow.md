---
layout: two-cols-header
---

# Run the workflow

You can provide arguments via another file:

::left::

```yaml [run.yml]
reads:
  - class: File
    path: ../../assays/rnaseq/dataset/blau1_CGATGT_L005_R1_002.fastq.gz
  - class: File
    path: ../../assays/rnaseq/dataset/blau2_TGACCA_L005_R1_002.fastq.gz
```


::right::

<div class="scale-75 origin-top">

```mermaid
flowchart TD
   f1 ---p1--> f3("QualityReport (*_fastqc.zip, *_fastqc.html)")
  subgraph run.yml
   f1("reads (*.fastq.gz)")
  end  

subgraph p1[workflow.cwl]
      p1-1{{FastQC}}
      d(fastqc docker) --- p1-1
  end
```

</div>


