MAIN FILE:
command: java -jar MultistartTS.jar <folder>
example: java -jar MultistartTS.jar resources/smallinstances/
output: M-TS-CCMP.xlsx


##############################
########  EXPERIMENTS ########
##############################

GREEDY CONSTRUCTIVE EXPERIMENT:
command: java -jar GreedyConstructiveIterations.jar <folder>
example: java -jar GreedyConstructiveIterations.jar resources/smallinstances/
output: GreedyConstructiveAfter1iterations.xlsx, GreedyConstructiveAfter5iterations.xlsx, GreedyConstructiveAfter10iterations.xlsx.
	GreedyConstructiveAfter20iterations.xlsx, GreedyConstructiveAfter30iterations.xlsx, GreedyConstructiveAfter40iterations.xlsx, 
	GreedyConstructiveAfter50iterations.xlsx


GREEDY  vs RANDOM CONSTRUCTIVE EXPERIMENT:
command: java -jar GreedyVSRandomConstructive.jar <folder>
example: java -jar GreedyVSRandomConstructive.jar resources/smallinstances/
output: ConstructiveGreedy1Second.xlsx, ConstructiverRandom1Second.xlsx


LOCAL SEARCH STRATEGIES:
command: java -jar LocalSearchStrategies.jar <folder>
example: java -jar LocalSearchStrategies.jar resources/smallinstances/
output: LS.xlsx, LS+E.xlsx, LS+E+ROI.xlsx