# Use Case 21: Model Consumed

## Description

* As an Application Developer I want to integrate or test model inference endpoints with amy application.
* As a Data Scientist I want to test my model inference endpoints and share the inference endpoint URL with my team.
* As an MLOps Engineer I want to unit test and performance test my model inference endpoints.

## Inputs

API spec, model API endpoint

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

    A[API spec, model API endpoint]
    style A fill:green

    B((Model consumed))
    style B fill:orange

    C[Model response]
    style C fill:blue

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
