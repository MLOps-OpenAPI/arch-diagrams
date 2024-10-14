# Use Case 7: Data Card Finalized

## Description

As a data manager, I want my data card in a final form so that the dataset quality is communicated to customers.

## Inputs

Draft data card; data curation description; data test report

## Output

Final data card

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

    A[Draft data card; data curation description; data test report]
    style A fill:green

    B((Data card finalized))
    style B fill:orange

    C[Final data card]
    style C fill:blue

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Inputs stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0

```


## Success path

1. Data distribution matches customer use case
2. Data provenance established
3. Label quality verified
4. Data trends follow expected results
5. Data trends are internally consistent
6. Adequate explanation when data trends do not follow
7. Metadata transforms match with data at each stage

## Exceptions/Errors

1. Data distribution does not match customer use case
2. Data provenance not established
3. Labels do not match ground truth
4. Unexplained data anomalies found
