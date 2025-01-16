# Use Case 16: Model Marketplace

## Description

As a <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#data-scientists">Data Scientist</a>, <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#product-managers">Product Manager</a> or <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#ml-engineers">ML Engineer</a>, I want to publish models in a secure way so that other authorized users can download and use them.

## Inputs

* Data card
* Model card
* Model upload URI
* List of Marketplace URIs* 

\* = optional input; defaults pulled from Settings

## Output

Model marketplace entry URI

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
                A3
                A4
            end
            subgraph Events ["**Events**"]
                B
            end
            subgraph Success ["**Success Path**"]
                C
            end
            subgraph End ["**End**"]
                E
            end
            subgraph Outputs ["**Outputs**"]
                D
            end
        end
        Inputs-->B
        %%C--> | test text | D
        B-->C
        C--> |Yes | D
        C--> |No | E
        %%D--> | test text | E
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A1[Data card]
    style A1 fill:blue

    A2[Model card]
    style A2 fill:blue

    A3[Model upload URI]
    style A3 fill:blue

    A4[List of Marketplace URIs]
    style A4 fill:blue

    B((Model advertised))
    style B fill:#660066

    C{Valid?}
    style C fill:#666600

    D[Model marketplace entry URI]
    style D fill:green

    E((Exceptions/Errors))
    style E fill:#990033

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Events stroke-width:0
    style End stroke-width:0
    style Success stroke-width:0
    style Outputs stroke-width:0

```


## Success path

1. The model is uploaded to the marketplace and is available for authorized users to download.

## Exceptions/Errors

1. The model is not uploaded successfully.
2. Unauthorized users **do not** have access to download the model.
3. Inability to upload the model.