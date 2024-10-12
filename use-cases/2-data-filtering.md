# Use Case 2: Data Filtering

## Description

As a data manager, I want my dataset filtered so that it only contains information relevant to my use case(s).

## Inputs

One or more refined use case documents;
Raw data from intake location

## Output

Filtered dataset

```mermaid

%% Creating a left-to-right flowchart
%% Learn the syntax here: https://mermaid.js.org/syntax/flowchart.html
%% Note: flowchart and graph are the same in Mermaid
graph LR;

    %% Define the common flow items:
    A--> | Data Intake | B
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

    B[Raw Data from Intake; One or more refined Use Cases]
    style B fill:green

    C((Data Filtering))
    style C fill:orange

    D[Filtered Dataset]
    style D fill:blue

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Inputs stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0

```


## Success path

1. Raw data filtered according to use case(s)
2. Data transformations recorded as metadata *

\* = required steps

## Exceptions/Errors

1. Metadata not recorded
2. Transformations could not be executed