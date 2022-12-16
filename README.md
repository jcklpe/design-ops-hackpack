# design-ops-hackpack
Template repo for bootstrapping a desOps practice using github.

Work in Progress. More to come soon.

## Design System Governance
```mermaid
graph TB
    subgraph Design System Working Group Context
        direction TB
        DESIGNIT--create-->NEW[/Document component needs <br/>and design in a git repo ticket/]
        NEW-->DISCUSS[Discuss new spec.]
        DISCUSS-->JSON[Write JSON Component specs]
        JSON-->PULL[Make pull request with proposed <br/> changes outlined in the JSON specs]
        PULL-->TEST{Test for consensus?}
        TEST--yes-->SPEC[Consensus achieved. <br/>Spec passes]
        TEST--no-->CONCERN{Raise concerns?}
        CONCERN--no-->ASIDE[Stand aside.]
        CONCERN--yes-->DISCUSS
        ASIDE-->SPEC


        DESIGNCHANGES-->PROPOSECHANGES[/Document proposed needs and design changes <br/> in git repo ticket./]
        PROPOSECHANGES-->DISCUSSEDIT[Discuss edits.]
        DISCUSSEDIT-->JSONEDIT[Edit existing <br/> JSON Component specs]
        JSONEDIT-->PULLEDIT[Make pull request with proposed changes <br/>outlined in the JSON specs]
        PULLEDIT-->TESTEDIT{Test for consensus?}
        TESTEDIT--yes-->SPEC[Consensus achieved. <br/>Spec passes]
        TESTEDIT--no-->CONCERNEDIT{Raise concerns?}
        CONCERNEDIT--no-->ASIDEEDIT[Stand aside.]
        CONCERNEDIT--yes-->DISCUSSEDIT
        ASIDEEDIT-->SPEC
    end

    subgraph Product Team Context
        direction TB
        START([design needed]) --> EXIST{Does the component style or <br/>pattern exist in <br/>the design system?}
        EXIST--yes--> CHANGES{Does the component need <br/>any changes to fit a new use case?}
        EXIST--no--> DESIGNIT[ Design component as you need for your product team context.]
        CHANGES--no--> END([Design app according to established spec])
        CHANGES--yes--> DESIGNCHANGES[Create a variant of the component<br/> according to the necessary changes<br/> needed in your product line ]
    SPEC-->END
    end


```