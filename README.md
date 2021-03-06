# ECS171 Project -- Pacman

We applied several machine learning techniques to play the game Pacman. We tried out Q-learning, Approximate Q-Learning and MiniMax algorithm to train the Pacman game.

## Built With/Version

* Depend on the configuration of local python
* Recommend Python 3

## Game and some useful flags

### Play the original pacman game manually

```
python/python(+version) pacman.py
```

### flags

* -h  please use -h for more options
* -p  <Agents> Ex: MinimaxAgent, AlphaBetaAgent, ExpectimaxAgent, AppxQAgent, ClassicQAgent
* -l  <Map> Maps are in diretory layout. Ex: smallGrid, mediumClassic, originClassic
* -n  <Number> The number of games to play
* -q  Disable game display window to let the game run faster
* -a  depth=<Number>, set the depth
      evalFn=<EvaluationFunction>, specify the following Evaluation Functions
* -x  NUMTRAINING, --numTraining=NUMTRAINING How many episodes are training (suppresses output) [Default: 0]
  
## MiniMax, AlphaBetaAgent and Expectimax

```
cd Project/pacmanAdversialSearch/
```

### Training with agents

To see the pacman game with depth 2:

```
python/python(+version) pacman.py -p ExpectimaxAgent -a depth=2 -a evalFn=EvaluationFunction_4features
python/python(+version) pacman.py -p AlphaBetaAgent -a depth=2 -a evalFn=EvaluationFunction_6features
```

Run the pacman game for 500 times with expectimax agent and depth 4, the display window is turned off: 

```
python/python(+version) pacman.py -p ExpectimaxAgent -a depth=4 -q -a evalFn=EvaluationFunction_6features
```

Run the pacman game for 500 times with minimax agent and depth 2

```
python/python(+version) pacman.py -p MinimaxAgent -n 500 -a depth=2 -q
```

Run the pacman game for 500 times with AlphabetaAgent agent and depth 2: 

```
python/python(+version) pacman.py -p AlphaBetaAgent -n 500 -a depth=3 -q -a evalFn=EvaluationFunction_4features
```

## Q-learning and Approximate Q-learning

```
cd Project/pacmanLearning/
```

### Training with Q-learning

Train on the smallGrid layout with Q-learning agent, 1500 episodes and test with 100 games
```
python/python(+version) pacman.py -p ClassicQAgent -x 1500 -n 1600 -l smallGrid
```

### Training with Approximate Q-learning

Train on the mediumClassic layout with Approximate Q-learning agent, selected features specified by SimpleExtractor, 30 episodes and test with 50 games
```
python/python(+version) pacman.py -p AppxQAgent -a extractor=SimpleExtractor -x 30 -n 80 -l mediumClassic
```

### Training with Approximate Q-learning
Train on the mediumClassic layout with Deep Q-learning agent, 1000 episodes and test with 10 games
```
python/python(+version) pacman.py -p DeepQAgent -x 1000 -n 1010 -l mediumClassic
```

## R code

Plots and statistical values can be found in `results.pdf` in R code directory. Using R studio or other applications that support `.rmd` file can reproduce the plots and data.
