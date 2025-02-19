# Use Case 7: Data Test (optional)

## Description

As a <a href='https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#data-scientists'>Data Scientist</a>, I want my curated datasets tested so that I can have confidence in the data.

## Inputs

* Draft data card
* Curated data
* Metadata for transforms
* Ground truth labels*

\* = optional input

## Output

* Data test report 

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

    A2[Curated data]
    style A2 fill:blue

    A3[Metadata for transforms]
    style A3 fill:blue

    A4[Ground truth labels]
    style A4 fill:#006d99

    B((Data Test))
    style B fill:#660066

    C{Valid?}
    style C fill:#666600

    D((Exceptions/Errors))
    style D fill:#990033

    E[Data test report]
    style E fill:green

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0
    style End stroke-width:0
    style Success stroke-width:0
```


## Success path

1. Data distribution matches customer use case
2. Data provenance established
3. Label quality verified
4. Data trends follow expected results
5. Data trends are internally consistent
6. Adequate explanation when data trends do not follow
7. Metadata transforms match with data at each stage

## Exceptions/Errors

1. Data distribution does not match customer use case
2. Data provenance not established
3. Labels do not match ground truth
4. Unexplained data anomalies found
