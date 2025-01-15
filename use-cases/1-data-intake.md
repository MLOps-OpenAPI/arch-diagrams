# Use Case 1: Data Intake

## Description

As a <a href='https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#data-scientists'>data scientist</a> or  <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#product-managers">product manager</a>, I want to upload raw data and associated background information into my data environment so that I can track its format, contents and lineage.

## Inputs

* Raw data
* Data collection form

## Output

* Raw data
* Naming standard
* Draft data card

```mermaid

%% Creating a left-to-right flowchart
%% Learn the syntax here: https://mermaid.js.org/syntax/flowchart.html
%% Note: flowchart and graph are the same in Mermaid
graph LR;

    %% Define the common flow items:
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
        B-->C
        %%C--> | test text | D
        C--> | No | D
        C--> | Yes | E
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A1[Raw data]
    style A1 fill:blue

    A2[Data collection form]
    style A2 fill:blue

    B((Data Intake))
    style B fill:#660066

    C{Valid?}
    style C fill:#666600

    D((Exceptions/Errors))
    style D fill:#990033

    E[Raw data; Naming standard; Draft data card]
    style E fill:green

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Inputs stroke-width:0
    style Events stroke-width:0
    style Success stroke-width:0
    style Outputs stroke-width:0
    style End stroke-width:0

```

## Success path

1. Data collection form contents validated
2. Draft data card created
3. Data collection form contents moved into data card
4. Raw data filename defined from data card contents + naming standard
5. Raw data with correct filename uploaded to data environment

## Exceptions/Errors

1. Data collection form incomplete
2. Data card could not be created
3. Data environment inaccessible
