# Use Case 14: Container Security Scan (optional)

## Description

As a <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#security--compliance-officers">Security Officer</a> or <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#ml-engineers">ML Engineer</a>, I want model containers hardened so that I can reduce vulnerabilities to make the containers resilient against security threats.

## Inputs

* Security standard
* Containerized model

## Output

* Hardened model container

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
        Inputs-->B
        B-->C
        C--> | No | D
        C--> | Yes | E
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A1[Security standard]
    style A1 fill:blue

    A2[Containerized model]
    style A2 fill:blue

    B((Container hardened))
    style B fill:#660066

    C[Hardened model container]
    style C fill:blue

    C{Valid?}
    style C fill:#666600

    D((Exceptions/Errors))
    style D fill:#990033

    E[Hardened model container]
    style E fill:green

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0
    style End stroke-width:0
    style Success stroke-width:0
```


## Success path

1. Model container hardened
    
## Exceptions/Errors

1. Scan failed
