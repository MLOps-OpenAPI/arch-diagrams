# Use Case 12: Model containerized

## Description

As a Data Scientist or ML Engineer, I want models packaged in a container so that I can ensure consistent and isolated execution across different computing environments.

## Inputs

OCI containerization standard;
Trained model

## Output

Containerized model

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
            subgraph Success ["**Success**"]
                C
            end
            subgraph End ["**End**"]
                D
            end
            subgraph Outputs ["**Outputs**"]
                E
            end
        end
        A-->B
        B-->C
        C--> | No | D
        C--> | Yes | E
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A[OCI containerization standard; trained model]
    style A fill:green

    B((Model containerized))
    style B fill:orange

    C{Valid success path?}
    style C fill:yellow

    D((Exceptions/Errors))
    style D fill:red

    E[Containerized model]
    style E fill:blue

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Inputs stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0
    style End stroke-width:0
    style Success stroke-width:0

```


## Success path

1. Dependencies identified
2. Container(s) generated
3. Needed ports opened
4. Service configuration file generated
5. Software bill of materials generated
    
## Exceptions/Errors

1. Dependencies not identified
2. Containers not generated
3. Cannot open necessary ports