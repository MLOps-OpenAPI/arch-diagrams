# Use Case 20: Model Monitoring (optional)

## Description

As an <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#ml-engineers">ML Engineer</a>, <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#data-scientists">Data Scientist</a>, <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#product-managers">Product Manager</a>, or a <a href="https://github.com/MLOps-OpenAPI/arch-diagrams?tab=readme-ov-file#3rd-party-tester">3rd party tester</a> I want to monitor AI models to ensure their accuracy, reliability, and value. Monitoring for Model drift, data quality, bias and fairness, security, and compliance should be considered for implementation when deploying models. 

Models may be continuously monitored, resources may be limited and pruning/filtering could be necessary.

## Inputs

* Alert thresholds
* Runtime events
    * User interactions: specific inference requests
    * Ongoing interactions: continuous inference requests
    * Non-inference interactions: other interactions that could be useful in debugging
* System resource events (optional)
* Logging level (optional)


## Output

* Performance report
* Alert outputs

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
                A4
            end
            subgraph Events ["**Events**"]
                B
            end
            subgraph Success ["**Success Path**"]
                C
            end
            subgraph End ["**End**"]
                E
            end
            subgraph Outputs ["**Outputs**"]
                D1
                D2
            end
        end
        Inputs-->B

        %%C--> | test text | D
        B-->C
        C--> | Yes | Outputs
        C--> | No | E
        %%D--> | test text | E
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A1[Runtime events]
    style A1 fill:blue

    A2[Alert thresholds]
    style A2 fill:blue

    A3[System resource events]
    style A3 fill:blue

    A4[Logging level]
    style A4 fill:blue

    B((Model monitoring))
    style B fill:#660066

    C{<b>Valid?</b>}
    style C fill:#666600

    E((<b>Exceptions/Errors</b>))
    style E fill:#990033

    D1[Performance report]
    style D1 fill:green

    D2[Alert outputs]
    style D2 fill:green

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Events stroke-width:0
    style End stroke-width:0
    style Success stroke-width:0

```


## Success path

1. Models are monitored
2. Model metrics are logged at configured level(s)
3. Alerts are raised when thresholds are reached on metrics that are monitored

## Exceptions/Errors

1. Metrics not being collected/logged
2. Events not being raised from metrics that are monitored 
