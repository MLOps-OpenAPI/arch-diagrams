# Use Case 17: Model Downloads (optional)

## Description

* As an <a href='https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#ai-engineers--intelligent-app-developers'>AI Engineers/Intelligent App Developers</a> I want to integrate or test model inference endpoints with any application.
* As a <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#data-scientists">Data Scientist</a> I want to test my model inference endpoints and share the inference endpoint URL with my team.
* As an <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#mlops-engineers">MLOps Engineer</a> I want to unit test and performance test my model inference endpoints.
* As an <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#quality-assurance-qa-engineers">Quality Assurance (QA) Engineer</a> I want to test models for stability and performance.
* As an <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#security--compliance-officers">Security & Compliance Officers</a> I want to make sure the model adheres to security protocols.

* As an <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#ml-engineers">ML Engineer</a>, <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#data-scientists">Data Scientist</a>, <a href='https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#ai-engineers--intelligent-app-developers'>AI Engineers/Intelligent App Developers</a>, <a href='https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#3rd-party-tester'>3rd party tester</a>, or <a href='https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#security--compliance-officers'>Security & Compliance Officer</a> I want to download secure models with knowledge of the data the model was trained on as well as details of the model.

## Inputs

* Selected Model Marketplace entry
* Model API endpoint
* Deployment document

## Output

* Containerized model
* Model card
* Data card

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
            subgraph Inputs ["**Input**"]
                A1
                A2
                A3
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
                E3
            end
        end
        Inputs-->B
        C--> | No | D
        B-->C
        C--> | Yes | Outputs
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A1[Selected Model Marketplace entry]
    style A1 fill:blue

    A2[Model API endpoint]
    style A2 fill:blue

    A3[Deployment Document]
    style A3 fill:blue

    B((Model consumed))
    style B fill:#660066

    C{Valid?}
    style C fill:#666600

    D((Exceptions/Errors))
    style D fill:#990033

    E1[Containerized model]
    style E1 fill:green

    E2[Model card]
    style E2 fill:green

    E3[Data card]
    style E3 fill:green

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Events stroke-width:0
    style End stroke-width:0
    style Success stroke-width:0
```


## Success path

1. A valid model, model card, and data card are downloaded.

## Exceptions/Errors

1. Model, model card, or data card not fully downloaded.
