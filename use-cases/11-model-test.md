# Use Case 11: Model test (optional)

## Description

As a <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#data-scientists">Data Scientist</a>, I want models tested so that I can have confidence in their results.

## Inputs

* Trained model
* Test strategy
* Testing tools

## Output

* Test results

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
        Inputs-->B
        B-->C
        C--> | No | D
        C--> | Yes | E
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A1[Trained model]
    style A1 fill:blue

    A2[Test strategy]
    style A2 fill:blue

    A3[Testing tools]
    style A3 fill:blue

    B((Model tested))
    style B fill:#660066

    C{Valid?}
    style C fill:#666600

    D((Exceptions/Errors))
    style D fill:#990033

    E[Model test report]
    style E fill:green

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0
    style End stroke-width:0
    style Success stroke-width:0

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
6. Test report incomplete; test strategy not followed