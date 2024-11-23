# Use Case 3a: Feature Engineering

## Description

As a <a href='https://github.com/MLOps-OpenAPI/arch-diagrams/blob/main/README.md#data-scientists'>data scientist</a> or <a href='https://github.com/MLOps-OpenAPI/arch-diagrams/blob/main/README.md#data-engineers'>data engineer</a> I want to extract, transform, and select the most relevant data from my datasets to produce high-quality ML models.

## Inputs

* Filtered data
* Labeled data

## Output

* Features data

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
            end
            subgraph Inputs ["**Inputs**"]
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
        A1-->B
        A2-->B
        B-->C
        C--> | No | D
        C--> | Yes | E
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A1[<b>Filtered data</b>]
    style A1 fill:#96c48b

    A2[<b>Labeled Data</b>]
    style A2 fill:#96c48b

    B((<b>Feature Engineering</b>))
    style B fill:#eda57e

    C{<b>Valid?</b>}
    style C fill:#f1f2b3

    D((<b>Exceptions/Errors</b>))
    style D fill:#e05e65

    E[<b>Feature data</b>]
    style E fill:#75a4f0

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Inputs stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0
    style End stroke-width:0

```


## Success path

1. Features extracted
2. Features stored in feature store (optional)

## Exceptions/Errors

1. Feature store not available
2. Features not extracted