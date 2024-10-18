# Use Case 16: Model Card

## Description

As a Data Scientist and MLOps Engineer I want a model card that contains details about the model.

## Inputs

Evaluation results, model info, assumptions summary, test results, risk assessment results, TORC score

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

    A[Evaluation results, model info, assumptions summary, test results, risk assessment results, TORC score]
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

1. A model card is created with the required information.

## Exceptions/Errors

1. The model is not created successfully.
2. Required information is not included on the model card.
