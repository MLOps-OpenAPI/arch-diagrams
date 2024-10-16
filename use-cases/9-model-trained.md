# Use Case 9: Model trained

## Description

As a ML engineer, I want my model trained so that I can make predictions on new unseen data.

## Inputs

Trainable data from curated ML-ready dataset; ML algorithm hyperparameters

## Output

Trained model; Model weights


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

    A[Trainable data from curated ML-ready dataset; ML algorithm hyperparameters]
    style A fill:green

    B((Model training))
    style B fill:orange

    C[Trained model; model weights]
    style C fill:blue

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Inputs stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0

```


## Success path

1. ML algorithm hyperparameters recorded as metadata
2. ML training details recorded as metadata
3. Trained model as artifact
4. Model weights as artifact

## Exceptions/Errors

1. Metadata not recorded
2. Training data not model-compatible
3. Artifacts not stored