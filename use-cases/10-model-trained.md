# Use Case 10: Model trained

## Description

As an <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#ml-engineers">ML Engineer</a> or a <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#data-scientists">Data Scientist</a>, I want my model trained so that I can make predictions on new unseen data.

## Inputs

* Trainable data from curated ML-ready dataset
* ML algorithm hyperparameters in JSON format

## Output

* Trained model
* Model weights


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

            subgraph Inputs ["**Inputs**"]
                A1
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
                E1
                E2
            end
        end
        Inputs-->B
        B-->C
        C--> | No | D
        C--> | Yes | Outputs
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A1[Trainable data from curated ML-ready dataset]
    style A1 fill:blue

    A2[ML algorithm hyperparameters in JSON format]
    style A2 fill:blue

    B((Model training))
    style B fill:#660066

    C{Valid?}
    style C fill:#666600

    D((Exceptions/Errors))
    style D fill:#990033

    E1[Trained model]
    style E1 fill:green
    
    E2[Model weights]
    style E2 fill:green
    
    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Events stroke-width:0
    style End stroke-width:0
    style Success stroke-width:0


```


## Success path

1. ML algorithm hyperparameters recorded as metadata
2. ML training details recorded as metadata
3. Trained model as artifact
4. Model weights as artifact

## Exceptions/Errors

1. Incompatible hyperparameter format
2. Metadata not recorded
3. Training data not model-compatible
4. Artifacts not stored