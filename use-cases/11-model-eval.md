# Use Case 11: Model evaluation

## Description

As a test engineer, I want tests evaluated so that I can provide evidence that model results meet user requirements.

## Inputs

Evaluation strategy;
Test results

## Output

Evaluation results;
Plan of Actions and Milestones entries

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

    A[Trained model; Test strategy; Test plan; Test data]
    style A fill:green

    B((Model evaluated))
    style B fill:orange

    C[Evaluation results; POA&M entries]
    style C fill:blue

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Inputs stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0

```


## Success path

1. Evaluation results generated
2. Security/vulnerability results generated
    
## Exceptions/Errors

1. Evaluation incomplete
2. Container not accessible