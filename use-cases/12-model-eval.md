# Use Case 12: Model evaluation

## Description

As a <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#data-scientists">Data Scientist</a>, I want tests evaluated so that I can provide evidence that model results meet user requirements.

## Inputs

* Trained model
* Evaluation strategy
* Test plan
* Test data

## Success

* Evaluation results
* Model remediation plan

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

    A1[Trained model]
    style A1 fill:blue

    A2[Evaluation strategy]
    style A2 fill:blue

    A3[Test plan]
    style A3 fill:blue

    A4[Test data]
    style A4 fill:blue

    B((Model evaluated))
    style B fill:#660066

    C{Valid?}
    style C fill:#666600

    D((Exceptions/Errors))
    style D fill:#990033

    E1[Evaluation results]
    style E1 fill:green

    E2[Model remediation plan]
    style E2 fill:green

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Events stroke-width:0
    style End stroke-width:0
    style Success stroke-width:0

```


## Success path

1. Evaluation results generated
2. Model remediation plan generated
    
## Exceptions/Errors

1. Evaluation incomplete
2. Model remediation plan could not be determined