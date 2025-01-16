# Use Case 15: Model card created (optional)

## Description

* As a <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#ml-engineers">ML Engineer</a>, <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#data-scientists">Data Scientist</a>, or <a href='https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#ai-engineers--intelligent-app-developers'>AI Engineers/Intelligent App Developers</a>, I want to understand enough of the ML model methodology and evaluation so that I can trust its outputs.

## Inputs

* Model test results
* Model evaluation results
* Model overview (required)
* Model SALE (Summary of Assumptions, Limitations and Errors/Exceptions)
* TORC score (optional)

## Output

Model card

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
                A5
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
        C--> | No | D
        B-->C
        C--> | Yes | E
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A1[Model test results]
    style A1 fill:blue

    A2[Model evaluation results]
    style A2 fill:blue

    A3[Model overview]
    style A3 fill:blue

    A4[Model SALE]
    style A4 fill:blue

    A5[TORC score]
    style A5 fill:#006d99

    B((Model card created))
    style B fill:#660066

    C{Valid?}
    style C fill:#666600

    D((Exceptions/Errors))
    style D fill:#990033

    E[Model card]
    style E fill:green

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
        style Events stroke-width:0
    style End stroke-width:0
    style Success stroke-width:0
    style Outputs stroke-width:0

```


## Success path

1. Model test results parsed
2. Model evaluation results parsed
3. Model overview parsed
4. Model SALE parsed
5. TORC score read
6. Model card generated

## Exceptions/Errors

1. Model test results incomplete
2. Model evaluation results incomplete
3. Model overview incomplete
4. Model SALE incomplete
5. TORC score missing
