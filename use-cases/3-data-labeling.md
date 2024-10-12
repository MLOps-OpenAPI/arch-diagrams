# Use Case 3: Data Labeling

## Description

As a data manager, I want my dataset labeled so that I can prepare it for machine learning.

## Inputs

Filtered data;
Object ontology

## Output

Filtered, labeled data

```mermaid

%% Creating a left-to-right flowchart
%% Learn the syntax here: https://mermaid.js.org/syntax/flowchart.html
%% Note: flowchart and graph are the same in Mermaid
graph LR;

    %% Define the common flow items:
    A--> | Data Filtering | B 
    %%A--> B
    %%B-->C
    subgraph Pipeline ["**Pipeline**"]
        
        %% Add an empty node to overcome some formatting issues
        subgraph invisibleSpace["<br/>"]

            %% Add the rest of the nodes
            subgraph Inputs ["**Inputs**"]
                B 
            end
            subgraph Events ["**Events**"]
                C
            end
            subgraph Outputs ["**Outputs**"]
                D
            end
        end
        B-->C
        %%C--> | test text | D
        C-->D
        %%D--> | test text | E
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A[Raw Data]
    style A fill:green

    B[Filtered Data]
    style B fill:green

    C((Data Labeling))
    style C fill:orange

    D[Filtered, labeled data]
    style D fill:blue

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Inputs stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0

```


## Success path

1. Objects identified according to ontology
2. Data labeling performed

## Exceptions/Errors

None