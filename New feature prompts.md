**Gian Maria Troiani**

**CLAUDE CODE \- AGENTIC CODING**

**STEPS IN THE WORKFLOW:**   
 1 \- Review & clean [EXECPLAN.md](http://EXECPLAN.md) (from previous work, if applicable)  
 2 \- Improve a prompt for a target feature  
 3 \- Research feature  
 4 \- Implement feature in [EXECPLAN.md](http://EXECPLAN.md)  
 5 \- Implement [EXECPLAN.m](http://EXECPLAN.md)d  
 6 \- Go back to step 1

1. **Review & clean [EXECPLAN.md](http://EXECPLAN.md)**  
   Review the additions to EXECPLAN.md. Also, make sure we don't keep in EXECPLAN.md outdated or superfluous information to make the document crisp.   
   It's imperative you don't delete the operational policy, guidance or instructions. Update the memory when appropriate and move operational policies out of milestones if necessary.   
   Before you are done, check you didn't delete any section that was used as operational guidance or instructions (eg MEMORY ACCESS PROTOCOLS, Slim EXECPLAN to Active Content Only. etc).   
   Check you didn't delete any section that was used as operational guidance or instructions even if you think you don't need to.  
     
   After you complete the above, even if you think you don't need to, you can delete NEW FEATURES.md if everything is fully implemented. If not everything is not fully implemented, delete the   
   text describing features that are already fully implemented.

2. **Improve a prompt for a target feature**  
   **Step A)** 

     
   Consider this prompt :   
     
     TARGET FEATURE \= "How to create a memory system for an AI. Initial research is provided in @agent\_memory\_memo.md and  
     @memory-systems-llm-ai-agents-research.md. The objective is to  
       create a memory system accessible (instructions on how to access it as needed to be provided in CLAUDE.md and EXECPLAN.md) for you to handle the increasing  
       complexity and length of the EXECPLAN effectively. The better you can access memories, the better you can help me and be more powerful. For example, an idea  
     would  
       be to take the milestones already achieved and bring them outside EXECPLAN.md but reference that s  
       hould they or their implementation be needed  they can be  
       accessed through an external file and provide the path to it."   
     
    Answer ".. '" if you understand

     
   **Step B)**  
     
   Following the style of the previous prompt, modify this prompt according to the context of the project:  
     
   \- essence of what you are trying to do and concept that you are trying to achieve   
     
 


3. **Research Feature (using agents)**  
     
   Create six sub-agents dedicated to researching RESEARCH\_TARGET given the insights distilled in RESEARCH DONE.   
   Give each sub-agent a distinct focus so the research is not duplicated (for example: UI and UX, data model and storage, upload pipeline, practice-question   
   generation flow, and system integration details).  
   In each subagent, produce a concise, implementation-ready writeup and add it to NEW FEATURES.md under a clearly labeled section for that worktree.  
   After all five writeups exist, consolidate them into a single cohesive plan for RESEARCH\_TARGET that matches the architecture and conventions already present in   
   the system.   
     
     Planning Phase Decisions:  
     \- Verify complex logic is correct  
     \- Ensure business requirements follow good practice  
     \- Establish clean service boundaries  
     \- Prevent unnecessary coupling    
     
   Again: After all five writeups exist, consolidate them into a single cohesive plan for   
   RESEARCH\_TARGET that matches the architecture and conventions already present in the system. Ultrathink  
     
     
   TARGET FEATURE \= "AlphaXiv-style document rendering for uploaded sources. Reference screenshot showing desired look:   
   ''/var/folders/cf/f08kwgss30scwpxr9tm32\_bw0000gn/T/TemporaryItems/NSIRD\_screencaptureui\_Jxu45U/Screenshot 2026-01-05 at 3.37.28 PM.png. The objective is to display uploaded documents in a clean,   
   readable format similar to how AlphaXiv renders research papers (three-panel layout with the document as the center focus). Two key requirements: (1) Users should be able to fully read the document   
   before starting practice questions, treating it as a study phase before assessment. (2) The document should remain persistently accessible in a 'Sources' section throughout the session, allowing users to  
    refer back to the original material at any point during practice. Think of it as separating the workflow into: upload → read/study → practice, with the source always one click away for reference. Leverage the research provided in RESEARCH DONE."   
     
    RESEARCH DONE \= @RESEARCH DONE.MD  
     
     
     
     
4. **Implement feature in EXECPLAN.md**  
   Update @EXECPLAN.MD to prepare to implement the new feature from @NEW FEATURES.md. Integrate the features into the current execplan.md to produce a new execplan according to the rules of @PLANS.md .

5. **Implement [EXECPLAN.md](http://EXECPLAN.md)**  
   Let's go ahead and implement @EXECPLAN.md. Refer to it often and follow the instructions in CLAUDE.md. Use chrome to test until the task succeeded. Proceed one milestone at a time. Before moving on to the following milestone, test all the logic of the current milestone, make sure no placeholders and that everything is well implemented and works. Make sure EXECPLAN.md is kept updated (all sections)  
     
   If you are undecided on how to proceed forward, spin up 3 git worktrees and to research or experiment with the potential options forward, then distill the learnings and go ahead with either the best way, or a mix of the best learnings from the research or experiments. 

