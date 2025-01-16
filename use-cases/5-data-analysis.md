# Use Case 4: Data Analysis (optional)

## Description

As a <a href='https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#data-scientists'>Data Scientist</a>, I want my dataset in an understandable form so that I can perform analysis on it.

## Inputs

* Filtered, labeled data

## Output

* Curated, descriptive data (human-readable and understandable)
* Metadata description of curation transforms for the input data

TODO: Figure out how to represent required metadata.

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
                A 
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
                E1
                E2
            end
        end
        A-->B
        B-->C
        C--> | Yes | Outputs
        C--> | No | D
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A[Filtered, Labeled Data]
    style A fill:blue

    B((Data Curation))
    style B fill:#660066

    C{Valid?}
    style C fill:#666600

    D((Exceptions/Errors))
    style D fill:#990033

    E1[Curated data, ready for data analysis]
    style E1 fill:green

    E2[Data curation description]
    style E2 fill:green

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Inputs stroke-width:0
    style Events stroke-width:0
    style End stroke-width:0
    style Success stroke-width:0

```


## Success path

1. Data annotations/descriptions added *
2. Curated data validated against schema/rules *
3. Data transformations recorded as metadata 
4. Metadata added to secure database
    

\* = optional steps

## Exceptions/Errors

1. Curated data does not match schema 
2. Curated data violates validation rules
3. Curated data could not be added to database
4. Metadata not recorded
5. Database not accessible
