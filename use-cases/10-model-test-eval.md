# Use Case 10: Model test and evaluation

## Description

As a test engineer, I want models evaluated so that I can have confidence in their results.

## Inputs

Trained model;
Test strategy;
Test plan;
Test data

## Output

Model test report

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

    B((Model testing))
    style B fill:orange

    C[Model test report]
    style C fill:blue

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Inputs stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0

```


## Success path

1. Test report generated
2. Data/metadata added to secure database
    
## Exceptions/Errors

1. One or more test cases not executed
2. Test data missing
3. Data could not be added to database
4. Metadata not recorded
5. Database not accessible
6. Test report incomplete