# Use Case 3: Data Labeling (optional)

## Description

As a <a href='https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#data-scientists'>Data Scientist</a> or <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#product-managers">Product Manager</a>, I want my dataset labeled so that I can prepare it for machine learning.

## Inputs

* Filtered data
* Object ontology

## Output

* Filtered, labeled data

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
                A1
                A2
            end
            subgraph Events ["**Events**"]
                B
            end
            subgraph Success ["**Success Path**"]
                C
            end
            subgraph End ["**End**"]
                D
            end
            subgraph Outputs ["**Outputs**"]
                E
            end
        end
        Inputs-->B
        B-->C
        %%C--> | test text | D
        C--> | No | D
        C--> | Yes | E
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A1[Filtered data]
    style A1 fill:blue

    A2[Object ontology]
    style A2 fill:blue

    B[Data labeling]
    style B fill:#660066

    C{Valid?}
    style C fill:#666600

    D((Exceptions/Errors))
    style D fill:#990033

    E[Filtered, labeled data]
    style E fill:green

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Events stroke-width:0
    style Success stroke-width:0
    style Outputs stroke-width:0
    style End stroke-width:0

```


## Success path

1. Objects identified according to ontology
2. Data labeling performed

## Exceptions/Errors

None