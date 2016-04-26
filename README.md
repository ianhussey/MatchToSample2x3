# One-to-Many Match to Sample Task for Two Three-Member Classes (MTS - OtM 3x3)

## License
Copyright (c) Ian Hussey 2016 (ian.hussey@ugent.be)

Distributed under the MIT license.

## Version
0.7.1 (22/4/2016)

- forked from MTS 3x3 version 0.7

Written in PsychoPy 1.82.01

*NB This implementation is still in development and has not been used in a study yet.* 

## Notes
- Trains two three-member classes: A1-B1-C1 and A2-B2-C2 via one-to-many match to sample training; then assesses for emergent C-B (equivalence) relations.
- Press return to end the task at the "end of task" screen.
- Includes R script in the "Analysis" folder which produces summaries of MTS performances, including demographic variables, pass/fail variables for both training and testing phases, and how many cycles of each were needed.
- All strings wihtin the task are set by the excel files. Easy to translate to other languages given there is full unicode support for non-english characters.
- The last row of a participant's .csv data file specifies whether they passed or failed the task under the "passed_training" and "passed_testing" columns record whether the mastery criterion was reached for each block. The R script extracts only the last repeat of each block in order to assess whether training and testing criteria were eventually passed or not.
- For demonstration and testing purposes the task present the stimuli as "A1", "C2" etc. To use word stimuli simply alter the stimuli.xlsx file (or replace it with the "stimuli ALT - ARBITRARY.xlsx" file which contains nonsense words.
- No support for image stimuli at present, but this would be trivial to add. For example, change TextComponents for ImageComponents and put image1.jpg etc in the stimulus file. All counterbalancing, block structure, etc is taken care of elsewhere.

## Task structure
*See the 'Explanation of task parameters' folder for illustrations of the task structure and the variables in the excel files that determine your parameters.*

- Training block contain X multiples of 8 trials, which each include a fully counterbalanced set of A1, A2 and A3 sample stimuli with the required target stimulus counterbalanced across all three stimuli locations. The location of the incorrect comparison stimuli is randomised for each trial.
- If the training crition of Y number of correct trials within a block is met, participants proceed to the testing block. 
- Otherwise, participants repeat the training block. This is done a max number of Z times.
- Testing block contains J multiples of 4 C-B (i.e. equivalence) trials. Symmetry relations could be added simply by modiying the task structure file.
-  If the testing crition of K number of correct trials within a block is met, the task ends with a "passed" message. 
-  Otherwise, participants repeat the testing block. This is done a max number of L times.
- If the max training or testing block repeats (Z or L) is reached, immediately after that block is finished the participant is recycled back to the start of the training blocks a maxiumum of Q number of times. 
- Note that the above means that if participant fail to meet the training criterion Z number of times they do not complete the testing blocks, but rather are given Q total opportunities to complete a max of Z number of training blocks, to meet the mastery criterion of Y trials out of X in each training block. This is somewhat abstract, but means that the task is trivial to adapt to the needs of your experimental design.
- NB By setting the training mastery criterion to 0 you can alter the structure of the task to that participants alwasys move from training to testing blocks, and therefore recieve loops of training and testing together rather than having to meet mastery criteria for each seperately. 

## Example task setups
In order to illustrate the flexibility of the current implimentation, three example setups are discussed below.

### Example setup 1
	training_criterion == 0
	testing_criterion == 7
	max_training == 1
	max_testing == 1
	max_training_and_testing == 10
	training_block_multiplier == 6
	testing_block_multiplier == 2
Participants will complete 1 block of 48 (i.e., 8\*6) training trials (A-B and A-C), and regardless of their performance on this block (because criterion = 0 and max = 1) it will be followed by 1 block of 8 (4\*2) testing trials (C-B). If they meet the testing criterion (>=7 correct) the task finishes, otherwise they will repeat this pair of training and testing blocks up to 9 additional times.

### Example setup 2
	training_criterion == 15
	testing_criterion == 8
	max_training == 20
	max_testing == 1
	max_training_and_testing == 2
	training_block_multiplier == 2
	testing_block_multiplier == 1
Participants will complete blocks of 16 (8\*2) training trials (A-B and A-C) until they meet the training mastery criterion (>=15 correct trials). They are provided with up to 20 opportunities to do so (i.e., 320 trials). If they meet the criterion, they will immediately complete a block of 8 (4\*2) testing trials (C-B). If they meet the testing criterion (>=7) the task finishes, otherwise they will go back to the training phase. However, they will only be provided with a max of two total opportunities to pass the testing block.

### Example setup 3
	training_criterion == 44
	testing_criterion == 7
	max_training == 10
	max_testing == 10
	max_training_and_testing == 1
	training_block_multiplier == 6
	testing_block_multiplier == 2
Using these settings, participants will complete blocks of 48 (8\*6) training trials (A-B and A-C) until they meet the training mastery criterion (>=44). They are provided with up to 10 opportunities to do so (i.e., 480 max trials). If they meet the training criterion, they will immediately complete blocks of 8 (4\*2) testing trials (C-B). Again, they will be provided with up to 10 opportunities to meet the criterion (>=7 correct), but will not be recycled back to the training phase after each failure or indeed at all. In this setup, participants must meet training and testing mastery criteria seperately to pass the task, but never recieve additional training once they have moved on to the testing phase.

## Known issues
None.

## To do
- Reasonable default parameters must be chosen, e.g., with reference to a specific previous experiment.

## Changelog
### 0.7.2
Updated readme and included 'explanations of task parameters' folder to illustrate different parameters of the task.

### 0.7.1
Forked from MTS 3x3 version 0.7. 
Removed code for shuffling the location of the second comparison stimulus, all references to the middle stimulus, and altered the stimuli files to refer to left and right stimuli rather than correct and incorrect.