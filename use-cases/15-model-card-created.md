# Use Case 15: Model card created

## Description

* As a <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#ml-engineers">ML Engineer</a>, <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#data-scientists">Data Scientist</a>, or <a href='https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#ai-engineers--intelligent-app-developers'>AI Engineers/Intelligent App Developers</a>, I want to understand enough of the ML model methodology and evaluation so that I can trust its outputs.

## Inputs

* Evaluation results
* Model info (required)
* Model SALE (Summary of Assumptions, Limitations and Errors/Exceptions)
* Model test results
* Risk assessment results
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
            end
            subgraph Inputs ["**Inputs**"]
                A2
            end
            subgraph Inputs ["**Inputs**"]
                A3
            end
            subgraph Inputs ["**Inputs**"]
                A4
            end
            subgraph Inputs ["**Inputs**"]
                A5
            end
            subgraph Inputs ["**Inputs**"]
                A6
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
        A4-->B
        A5-->B
        A6-->B
        C--> | No | D
        B-->C
        C--> | Yes | E
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A1[Evaluation results]
    style A1 fill:green

    A2[Model info]
    style A2 fill:green

    A3[Model SALE]
    style A3 fill:green

    A4[Model test results]
    style A4 fill:green

    A5[Risk assessment results]
    style A5 fill:green

    A6[TORC score]
    style A6 fill:green

    B((Model card created))
    style B fill:orange

    C{Valid?}
    style C fill:yellow

    D((Exceptions/Errors))
    style D fill:red

    E[Model card]
    style E fill:blue

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Inputs stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0

```


## Success path

1. Evaluation results parsed
2. Model info parsed
3. Model SALE parsed
4. Model test results parsed
5. Risk assessment parsed
6. TORC score read
7. Model card generated

## Exceptions/Errors

1. Evaluation results incomplete
2. Model info incomplete
3. Model SALE incomplete
4. Model test results incomplete
5. Risk assessment incomplete
6. TORC score missing
