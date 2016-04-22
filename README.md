# One-to-Many Match to Sample Task for Two Three-Member Classes (MTS - OtM 3x3)

## License
Copyright (c) Ian Hussey 2016 (ian.hussey@ugent.be)

Distributed under the MIT license.

## Version
0.7.1 (22/4/2016)

- forked from MTS 3x3 version 0.7

Written in PsychoPy 1.82.01

*NB This implementation is still in development and has not been used in a study yet.* 

## Task structure
Trains two three-member classes: A1-B1-C1 and A2-B2-C2 via one-to-many match to sample training; then assesses for emergent C-B (equivalence) relations.

- Training block contains 12 trials contain each contain a fully counterbalanced set of A1 and A2 sample stimuli with the required target stimulus counterbalanced across all three stimuli locations. The location of the incorrect comparison stimuli is randomised for each trial.
- If the training crition of X number of correct trials within a block is met, participants proceed to the testing block. Default is 10 (out of 12: 89%).
- Otherwise, participants repeat the training block. This is done a max number of times set by max_training.
- Testing block contains 6 C-B (i.e. equivalence) trials. Symmetry relations could be added simply by modiying the task structure file.
-  If the testing crition of x number of correct trials within a block is met, the task ends with a "passed" message. Default is 5 (out of 6: 89%).
- Otherwise, participants repeat both the training and testing blocks. Participants must again meet the training criterion to move on to the testing blocks. This is done a max number of times set by max_training_and_testing.
- By setting the training crition to 0 you can alter the structure of the task to that participants recieve loops of training and testing rather than requiring them to meet a training accuracy crition before being exposed to the testing blocks.  
- Includes working R script in analysis folder which will summarize MTS performances for you (e.g., pass/fail training/testing phases, and how many cycles of each were needed).

## Notes
- The last row of a participant's .csv data file specifies whether they passed or failed the task under the "passed_training" column.
- For demonstration and testing purposes the task present the stimuli as "A1", "C2" etc. To use word stimuli simply alter the stimuli.xlsx file (or replace it with the "stimuli ALT - ARBITRARY.xlsx" file which contains nonsense words.
- All instructions, stimuli and several task parameters are set via the "stimuli, instructions and parameters.xlsx" file.
- Full unicode support: one could use chinese characters etc as word stimuli, or tranlsate the task in to other languages simply by modifying the stimuli file. 
- No support for image stimuli at present, but this would be trivial to add. For example, change TextComponents for ImageComponents and put image1.jpg etc in the stimulus file. All counterbalancing, block structure, etc is taken care of elsewhere.
- Press return to end the task at the end of task screen.

## Known issues
None.

## To do
- Reasonable default parameters must be chosen, e.g., with reference to a specific previous experiment.

## Changelog
### 0.7.1
Forked from MTS 3x3 version 0.7. 
