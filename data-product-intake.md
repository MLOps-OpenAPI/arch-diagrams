# Use Case 4: Data Product Intake

## Description

As a data scientist, I want my dataset in an understandable form so that I can perform analysis on it.

## Inputs

Raw Data, Data Intake Form

## Output

Curated, descriptive data (human-readable and understandable);
metadata description of curation transforms for the input data.


```mermaid

%% Creating a left-to-right flowchart
%% Learn the syntax here: https://mermaid.js.org/syntax/flowchart.html
%% Note: flowchart and graph are the same in Mermaid
graph LR;

    %% Define the common flow items:
    %%A--> | Data Filtering | B--> | ??? | C
    A--> C
    B--> C
    subgraph Pipeline ["**Pipeline**"]
        
        %% Add an empty node to overcome some formatting issues
        subgraph invisibleSpace["<br/>"]

            %% Add the rest of the nodes
            subgraph Inputs ["**Inputs**"]
                C 
            end
            subgraph Events ["**Events**"]
                D
            end
            subgraph Outputs ["**Outputs**"]
                E
            end
        end
        C-->D
        %%C--> | test text | D
        D-->E
        %%D--> | test text | E
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A[Raw Data]
    style A fill:green

    B[Data Intake Form]
    style B fill:green

    C[Raw data, Data intake form]
    style C fill:green

    D((Data Product Intake))
    style D fill:orange

    E[Naming standard, raw data, data card]
    style E fill:blue

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Inputs stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0

```


## Success path

1. Data card
2. TODO
    

\* = required steps

## Exceptions/Errors

1. TODO
