# Use Case 1: Data Intake

## Description

As a data manager, I want to upload raw data and associated background information into my data environment so that I can track its format, contents and lineage.

## Inputs

Raw data;
Data intake form

## Output

Raw data;
Naming standard;
Data card

```mermaid

%% Creating a left-to-right flowchart
%% Learn the syntax here: https://mermaid.js.org/syntax/flowchart.html
%% Note: flowchart and graph are the same in Mermaid
flowchart LR

    %% Define the common flow items:
    subgraph Pipeline ["**MLOps Pipeline**"]
        direction LR
        %% Add an empty node to overcome some formatting issues
        subgraph dataPipeline["***Data Pipeline***"]
            %% Add the rest of the nodes
            subgraph Data Intake [<br/>]
                A 
            end
            subgraph Data Filtering 
                B
            end
            subgraph Data Labeling 
                C
            end
            subgraph Data Analysis 
                D
            end
            subgraph Data ML Ready 
                E
            end
            subgraph Data Test/Eval 
                F
            end
            subgraph dataCardFinal ["Data Card Final"]
                G
            end
        end

        A-->B
        B-->C
        C-->D
        D-->E
        E-->F
        F-->G

    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    A[Data Intake]
    style A fill:green

    B[Data Filtering]
    style B fill:green

    C[Data Labeling]
    style C fill:green

    D[Data Analysis]
    style D fill:green

    E[Data ML Ready]
    style E fill:green

    F[Data Test/Eval]
    style F fill:green

    G[Data Card Final]
    style G fill:green

    %% Remove unnecessary box outlines
    %%style invisibleSpace1 stroke-width:0
    %% style Data Intake stroke-width:0
    %% style Events stroke-width:0
    %% style Outputs stroke-width:0


    %% Define the common flow items:
    subgraph Pipeline ["**Model Pipeline**"]
        direction TB
        %% Add an empty node to overcome some formatting issues
        subgraph modelPipeline["***Model Pipeline***<br/>"]
            subgraph modelEval ["**Model Eval**"]
                H
            end
            subgraph Model Trained ["**Model Trained**"]
                I
            end
            subgraph Model Test ["**Model Test**"]
                J
            end
            subgraph Model Containerized ["**Model Containerized**"]
                K
            end
            subgraph Container Hardened ["**Container Hardened**"]
                L
            end
            subgraph Risk Assessment ["**Risk Assessment**"]
                M
            end
            subgraph Model Card Created ["**Model Card Created**"]
                N
            end
            subgraph Model Card ["**Model Card**"]
                O
            end
            subgraph Model Marketplace ["**Model Marketplace**"]
                P
            end
            subgraph Model Downloads ["**Model Downloads**"]
                Q
            end
            subgraph Model Deployment ["**Model Deployment**"]
                R
            end
            subgraph Model Consumed ["**Model Consumed**"]
                S
            end
            subgraph Model Monitoring ["**Model Monitoring**"]
                T
            end
        end
        
        %%G-->H
        H-->I
        I-->J
        J-->K
        K-->L
        L-->M
        M-->N
        N-->O
        O-->P
        P-->Q
        Q-->R
        R-->S
        S-->T

        %%dataCardFinal-->modelEval
        dataPipeline-->modelPipeline
    end

    %% Now label and style the blocks
    %% Note: You could have done this above, but I find this to be cleaner and easier to manage

    H[Raw data; Naming standard; Data card]
    style H fill:green

    I[Raw data; Naming standard; Data card]
    style I fill:green

    J[Raw data; Naming standard; Data card]
    style J fill:green

    K[Raw data; Naming standard; Data card]
    style K fill:green

    L[Raw data; Naming standard; Data card]
    style L fill:green

    M[Raw data; Naming standard; Data card]
    style M fill:green

    N[Raw data; Naming standard; Data card]
    style N fill:green

    O[Raw data; Naming standard; Data card]
    style O fill:green

    P[Raw data; Naming standard; Data card]
    style P fill:green

    Q[Raw data; Naming standard; Data card]
    style Q fill:green

    R[Raw data; Naming standard; Data card]
    style R fill:green

    S[Raw data; Naming standard; Data card]
    style S fill:green

    T[Raw data; Naming standard; Data card]
    style T fill:green

    %% Remove unnecessary box outlines
    %%style invisibleSpace2 stroke-width:0
    %% style Inputs stroke-width:0
    %%style Events stroke-width:0
    %%style Outputs stroke-width:0

```

## Success path

1. TBD

## Exceptions/Errors

1. TBD
