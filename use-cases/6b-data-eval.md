# Use Case 6: Data Evaluation

## Description

As a <a href='https://github.com/MLOps-OpenAPI/arch-diagrams/blob/main/README.md#data-engineer'>data engineer</a>, I want my curated datasets evaluated so that I can have confidence in the data.

## Inputs

* Data card*
* Curated data*
* Metadata for transforms*
* Ground truth labels

\* = required inputs

## Output

Data test report 

```mermaid

%% Creating a left-to-right flowchart
%% Learn the syntax here: https://mermaid.js.org/syntax/flowchart.html
%% Note: flowchart and graph are the same in Mermaid
graph LR;

    %% Define the common flow items:
    %%A--> B
    %%B-->C
    subgraph Pipeline ["**Pipeline**"]
        
        %% Add an empty node to overcome some formatting issues
        subgraph invisibleSpace["<br/>"]

            %% Add the rest of the nodes
            subgraph Inputs ["**Inputs**"]
                A
            end
            subgraph Events ["**Events**"]
                B
            end
            subgraph Success ["**Success**"]
                C
            end
            subgraph End ["**End**"]
                D
            end
            subgraph Outputs ["**Outputs**"]
                E
            end
        end
        A-->B
        B-->C
        C--> | No | D
        C--> | Yes | E
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A[Data card; curated data; metadata for transforms; ground truth labels if available]
    style A fill:green

    B((Data Evaluation))
    style B fill:orange

    C{Valid success path?}
    style C fill:yellow

    D((Exceptions/Errors))
    style D fill:red

    E[Data test report]
    style E fill:blue

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Inputs stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0
    style End stroke-width:0
    style Success stroke-width:0
```


## Success path

1. Data distribution matches customer use case
2. Data provenance established
3. Label quality verified
4. Data trends follow expected results
5. Data trends are internally consistent
6. Adequate explanation when data trends do not follow
7. Metadata transforms match with data at each stage

## Exceptions/Errors

1. Data distribution does not match customer use case
2. Data provenance not established
3. Labels do not match ground truth
4. Unexplained data anomalies found