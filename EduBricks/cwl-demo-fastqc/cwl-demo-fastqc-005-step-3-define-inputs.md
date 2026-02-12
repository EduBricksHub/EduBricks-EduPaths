---
layout: two-cols-header
---

# Step 3: Define inputs

::left::

```yaml [workflow.cwl] {12-19}
#!/usr/bin/env cwl-runner
cwlVersion: v1.2
class: CommandLineTool

hints:
  DockerRequirement:
    dockerPull: quay.io/biocontainers/fastqc:0.11.9--hdfd78af_1

baseCommand: ["fastqc"]

inputs:
  reads:
    type: File[]
    inputBinding:
      position: 1

arguments: 
  - valueFrom: $(runtime.outdir)
    prefix: "-o"
 
outputs: []
```

::right::

<div class="scale-75 origin-top">

```mermaid
flowchart TD
  f1("Reads (*.fastq)") ---p1
  subgraph p1[workflow.cwl]
      p1-1{{FastQC}}
      d(fastqc docker) --- p1-1
  end
```

</div>


