# Use Case 14: Risk profiled

## Description

As a security engineer, I want to profile data and model risks so that mitigation strategies and informed decisions can be made to lower risk.

## Inputs

Model test report;
Data test report;
Refined use case doc;
Trained model;
Risk assessment framework

## Output

Risk assessment

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

    A[Model test report; Data test report; Refined use case doc; Trained model; Risk assessment framework]
    style A fill:green

    B((Risk assessed))
    style B fill:orange

    C[Risk assessment]
    style C fill:blue

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Inputs stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0

```


## Success path

1. Risk assessment tools executed
2. Risk assessment generated
    
## Exceptions/Errors

1. Input missing
2. Input format incompatible with risk assessment tools
