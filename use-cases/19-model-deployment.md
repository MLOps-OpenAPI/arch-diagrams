# Use Case 19: Model Deployment

## Description

* As an <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#ml-engineers">ML Engineer</a>, <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#product-manager">Product Manager</a>, <a href='https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#ai-engineers--intelligent-app-developers'>AI Engineers/Intelligent App Developers</a>, or <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#security--compliance-officers">Security & Compliance Officers</a> I want to deploy models in a scalable and safe way.

## Inputs

* Containerized model (artifact or path)
* inference engine

## Output

Inference endpoint

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
        C--> | No | D
        B-->C
        C--> | Yes | E
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A1[Containerized model]
    style A1 fill:green

    A2[Inference engine]
    style A2 fill:green

    B((Model deployed))
    style B fill:orange

    C{Valid?}
    style C fill:yellow

    D((Exceptions/Errors))
    style D fill:red

    E[Inference endpoint]
    style E fill:blue

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Inputs stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0

```


## Success path

1. A model is deployed
2. Inference endpoint available

## Exceptions/Errors

1. Models not deployed
2. Inference endpoint not available
