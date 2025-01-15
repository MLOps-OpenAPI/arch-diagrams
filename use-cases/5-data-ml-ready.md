# Use Case 5: ML-ready data

## Description

As a <a href='https://github.com/MLOps-OpenAPI/arch-diagrams/blob/main/README.md#mlops-engineer'>ML engineer</a> and <a href='https://github.com/MLOps-OpenAPI/arch-diagrams/blob/main/README.md#data-scientists'>data scientist</a>, I want my dataset prepared so that I can perform machine learning on it.

## Inputs

* Curated data, ready for data analysis
* Data curation process
* Model type

## Output

* Curated data, ready for machine learning
* Data curation description

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
            end
            subgraph Inputs ["**Inputs**"]
                A2
            end
            subgraph Inputs ["**Inputs**"]
                A3 
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
        A3-->B
        B-->C
        C--> | Yes | E
        C--> | No | D
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A1[Curated Data, ready for data analysis]
    style A1 fill:blue

    A2[Data curation process]
    style A2 fill:blue

    A3[Model type]
    style A3 fill:blue

    B((Data Curation))
    style B fill:#660066

    C{Valid?}
    style C fill:#666600

    D((Exceptions/Errors))
    style D fill:#990033

    E[Curated data, ready for machine learning; Data curation description]
    style E fill:green

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Inputs stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0
    style End stroke-width:0
    style Success stroke-width:0
```


## Success path

1. Curated data matches up against model inputs *
2. Data transformations recorded as metadata 
3. Data/metadata added to secure database 

\* = optional steps

## Exceptions/Errors

1. Curated data does not match schema 
2. Curated data violates validation rules
3. Curated data could not be added to database
4. Metadata not recorded
5. Database not accessible
