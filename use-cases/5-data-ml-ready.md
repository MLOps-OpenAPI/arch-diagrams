# Use Case 5: Data Analysis

## Description

As a ML engineer, I want my dataset prepared so that I can perform machine learning on it.

## Inputs

Curated data, ready for data analysis;
Data curation process

## Output

Curated data, ready for machine learning;
Data curation description

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

    A[Filtered Data]
    style A fill:green

    B[Curated Data, ready for data analysis; Data curation process]
    style B fill:green

    C((Data Curation))
    style C fill:orange

    D[Curated Data, ready for machine learning; Data curation description]
    style D fill:blue

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Inputs stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0

```


## Success path

1. Curated data validated against schema/rules
2. Data transformations recorded as metadata *
3. Data/metadata added to secure database *
    

\* = required steps

## Exceptions/Errors

1. Curated data does not match schema 
2. Curated data violates validation rules
3. Curated data could not be added to database
4. Metadata not recorded
5. Database not accessible
