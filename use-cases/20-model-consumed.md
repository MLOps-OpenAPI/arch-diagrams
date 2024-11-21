# Use Case 20: Model Consumed

## Description

* As an <a href='https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#ai-engineers--intelligent-app-developers'>AI Engineers/Intelligent App Developers</a> I want to integrate or test model inference endpoints with any application.
* As a <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#data-scientists">Data Scientist</a> I want to test my model inference endpoints and share the inference endpoint URL with my team.
* As an <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#mlops-engineers">MLOps Engineer</a> I want to unit test and performance test my model inference endpoints.
* As an <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#quality-assurance-qa-engineers">Quality Assurance (QA) Engineer</a> I want to test models for stability and performance.
* As an <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#security--compliance-officers">Security & Compliance Officers</a> I want to make sure the model adheres to security protocols.

## Inputs

* API spec
* Model API endpoint
* Deployment document

## Output

Model response

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
            subgraph Input1 ["**Input**"]
                A1
            end
            subgraph Input2 ["**Input**"]
                A2
            end
            subgraph Input3 ["**Input**"]
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
                E
            end
        end
        A1-->B
        A2-->B
        A3-->B
        %%C--> | test text | D
        B-->C
        C--> | No | D
        C--> | Yes | E
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A1[API spec]
    style A1 fill:green

    A2[Model API endpoint]
    style A2 fill:green

    A3[Deployment Document]
    style A3 fill:green


    B((Model consumed))
    style B fill:orange

    C{Valid?}
    style C fill:yellow

    D((Exceptions/Errors))
    style D fill:red

    E[Model response]
    style E fill:blue

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Inputs stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0

```


## Success path

1. Models are accessible
2. Models return appropriate response

## Exceptions/Errors

1. Models not available
2. Models not returning correct response
