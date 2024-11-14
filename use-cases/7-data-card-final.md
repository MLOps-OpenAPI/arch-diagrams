# Use Case 7: Data Card Finalized

## Description

As a Product Manager, I want my [data card](https://sites.research.google/datacardsplaybook/) in a final form so that the dataset quality is communicated to customers.

## Inputs

Draft data card; data curation description; data evaluation report; data handling guidance*

\* = optional input

## Output

Final data card

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

    A[Draft data card; data curation description; data test report; data handling guidance if available]
    style A fill:green

    B((Data card finalized))
    style B fill:orange

    C{Valid success path?}
    style C fill:yellow

    D((Exceptions/Errors))
    style D fill:red

    C[Final data card]
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

1. All data card entries filled 

## Exceptions/Errors

1. One or more data card entries are unfilled
