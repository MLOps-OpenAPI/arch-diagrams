# Use Case 4: Feature Engineering (optional)

## Description

As a <a href='https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#data-scientists'>Data Scientist</a> or 
<a href='https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#data-engineers'>Data Engineer</a> 
I want to extract, select, and transform the most relevant data into features from my datasets to produce high-quality ML models. 

## Inputs

* Filtered data
* Labeled data

## Output

* Features derived from data

```mermaid

%% Creating a left-to-right flowchart
%% Learn the syntax here: https://mermaid.js.org/syntax/flowchart.html
%% Note: flowchart and graph are the same in Mermaid
graph LR;

    %% Define the common flow items:
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
        C--> | No | D
        C--> | Yes | E
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A1[<b>Filtered data</b>]
    style A1 fill:blue

    A2[<b>Labeled Data</b>]
    style A2 fill:blue

    B((<b>Feature Engineering</b>))
    style B fill:#660066

    C{Valid?}
    style C fill:#666600

    D((Exceptions/Errors))
    style D fill:#990033

    E[<b>Features derived from data</b>]
    style E fill:green

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Events stroke-width:0
    style Success stroke-width:0
    style Outputs stroke-width:0
    style End stroke-width:0

```


## Success path

1. Features derived from data
2. Features stored in feature store *

\* = optional steps

## Exceptions/Errors

1. Feature store not available
2. Features not extracted