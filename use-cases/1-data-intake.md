# Use Case 1: Data Intake

## Description

As a data manager, I want to upload raw data and associated background information into my data environment so that I can track its format, contents and lineage.

## Inputs

Raw data;
Data intake form

## Output

Raw data;
Naming standard;
Draft data card

```mermaid

%% Creating a left-to-right flowchart
%% Learn the syntax here: https://mermaid.js.org/syntax/flowchart.html
%% Note: flowchart and graph are the same in Mermaid
graph LR;

    %% Define the common flow items:
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

    A[Raw data; Data intake form]
    style A fill:green

    B((Data Intake))
    style B fill:orange

    C[Raw data; Naming standard; Draft data card]
    style C fill:blue

    %% Remove unnecessary box outlines
    style invisibleSpace stroke-width:0
    style Inputs stroke-width:0
    style Events stroke-width:0
    style Outputs stroke-width:0

```

## Success path

1. Data intake form contents validated
2. Draft data card created
3. Data intake form contents moved into data card
4. Raw data filename defined from data card contents + naming standard
5. Raw data with correct filename uploaded to data environment

## Exceptions/Errors

1. Data intake form incomplete
2. Data card could not be created
3. Data environment inaccessible
