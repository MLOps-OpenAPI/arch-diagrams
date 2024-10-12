# Use Case 4: Data Analysis

## Description

As a data scientist, I want my dataset in an understandable form so that I can perform analysis on it.

## Inputs

Filtered, labeled data

## Output

Curated, descriptive data (human-readable and understandable);
metadata description of curation transforms for the input data.


```mermaid

%% Creating a left-to-right flowchart
%% Learn the syntax here: https://mermaid.js.org/syntax/flowchart.html
%% Note: flowchart and graph are the same in Mermaid
graph LR;

    %% Define the common flow items:
    A--> | Data Filtering | B--> | Data Labeling | C
    %%A--> B
    %%B-->C
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

    B[Filtered Data]
    style B fill:green

    C[Filtered, Labeled Data]
    style C fill:green

    D((Data Curation))
    style D fill:orange

    E[Curated Data, ready for data analysis]
    style E fill:blue

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Inputs stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0

```


## Success path

1. Data annotations/descriptions added
2. Curated data validated against schema/rules
3. Data transformations recorded as metadata *
4. Data/metadata added to secure database *
    

\* = required steps

## Exceptions/Errors

1. Curated data does not match schema 
2. Curated data violates validation rules
3. Curated data could not be added to database
4. Metadata not recorded
5. Database not accessible
