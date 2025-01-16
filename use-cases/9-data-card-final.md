# Use Case 9: Data Card Finalized

## Description

As a <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#product-managers">Product Manager</a>, I want my [data card](https://sites.research.google/datacardsplaybook/) in a final form so that the dataset quality is communicated to customers.

## Inputs

* Draft data card
* Data curation description
* Data evaluation report
* Data handling guidance*

\* = optional input

## Output

* Final data card

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

    A1[Draft data card]
    style A1 fill:blue

    A2[Data curation description]
    style A2 fill:blue

    A3[Data test report]
    style A3 fill:blue

    A4[Data handling guidance]
    style A4 fill:#006d99

    B((Data card finalized))
    style B fill:#660066

    C{Valid?}
    style C fill:#666600

    D((Exceptions/Errors))
    style D fill:#990033

    E[Final data card]
    style E fill:green

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0
    style End stroke-width:0
    style Success stroke-width:0

```


## Success path

1. All data card entries filled 

## Exceptions/Errors

1. One or more data card entries are unfilled
