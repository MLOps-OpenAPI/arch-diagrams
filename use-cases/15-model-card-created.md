# Use Case 15: Model card created

## Description

As a user, I want to understand enough of the ML model methodology and evaluation so that I can trust its outputs.

## Inputs

Evaluation results;
Model info;
Model summary of Assumptions, Limitations and Errors/Exceptions;
Model test results;
Risk assessment results;
TORC score

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
                A
            end
            subgraph Events ["**Events**"]
                B
            end
            subgraph Outputs ["**Outputs**"]
                C
            end
        end
        A-->B
        %%C--> | test text | D
        B-->C
        %%D--> | test text | E
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A[Evaluation results; Model info; Model summary of Assumptions, Limitations and Errors/Exceptions; Model test results; Risk assessment results; TORC score]
    style A fill:green

    B((Model card created))
    style B fill:orange

    C[Model card]
    style C fill:blue

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
