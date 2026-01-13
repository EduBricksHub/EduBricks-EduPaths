---
layout: two-columns
---

# Step 1: Define CLI tool as CWL CommandLineTool

::left::

- Without in/out
- (Requires **local tool installed**)


```yaml [workflow.cwl]
#!/usr/bin/env cwl-runner
cwlVersion: v1.2
class: CommandLineTool

baseCommand: ["fastqc", "--help"]

inputs: []
 
outputs: []
```

::right::

```mermaid
flowchart TD
  subgraph p1[workflow.cwl]
      p1-1{{fastqc --help}}
  end
```


