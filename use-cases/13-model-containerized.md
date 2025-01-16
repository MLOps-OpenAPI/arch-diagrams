# Use Case 13: Model containerized (optional)

## Description

As a <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#data-scientists">Data Scientist</a> or <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#ml-engineers">ML Engineer</a>, I want models packaged in a container so that I can ensure consistent and isolated execution across different computing environments.

## Inputs

* OCI containerization standard
* Trained model

## Output

* Containerized model download path

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
        B-->C
        C--> | No | D
        C--> | Yes | E
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A1[OCI containerization standard]
    style A1 fill:blue

    A2[Trained model]
    style A2 fill:blue

    B((Model containerized))
    style B fill:#660066

    C{Valid?}
    style C fill:#666600

    D((Exceptions/Errors))
    style D fill:#990033

    E[Containerized model download path]
    style E fill:green

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