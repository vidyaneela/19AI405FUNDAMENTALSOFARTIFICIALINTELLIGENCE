# 19AI405 FUNDAMENTALS OF ARTIFICIALINTELLIGENCE 
# Laboratory Experiments
## ExpNo 1 : Implement Depth First Search Traversal of a Graph
### Name: VIDYA NEELA M
### Register Number: 212221230120
### Aim:
To Implement Depth First Search Traversal of a Graph using Python 3.

### Theory:
Depth First Traversal (or DFS) for a graph is like Depth First Traversal of a tree. The only catch here is that, unlike trees, graphs may contain cycles (a node may be visited twice). Use a Boolean visited array to avoid processing a node more than once. A graph can have more than one DFS traversal. Depth-first search is an algorithm for traversing or searching trees or graph data structures. The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking. Step 1: Initially, stack and visited arrays are empty.
![277147664-640b3c6f-3ac1-49a2-a955-68da9a71f446](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/61b9ddad-730a-4d09-996f-59ab7c5f015b)
Queue and visited arrays are empty initially. Stack and visited arrays are empty initially. Step 2: Visit 0 and put its adjacent nodes which are not visited yet into the stack

![277147583-86dcf7d9-1f9d-49b0-a821-5976a6e77606](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/0fe8be50-f0c2-4edf-9c7c-6a12b1a84009)
Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack

Step 3: Now, Node 1 at the top of the stack, so visit node 1 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack
![277147597-e6017942-08b1-4742-87ad-c97eb97bf985](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/163fe4c3-cb75-4212-97c2-938934b4dd7a)

Visit node 1 Visit node 1

Step 4: Now, Node 2 at the top of the stack, so visit node 2 and pop it from the stack and put all of its adjacent nodes which are not visited (i.e,3, 4) in the stack.
![image](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/431364a3-724a-4ed2-952d-f415e10b0b42)

Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack

Step 5: Now, Node 4 at the top of the stack, so visit node 4 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack. 

![277147620-20b76a05-5668-4da5-8189-e10fb1bb7238](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/dc4f6ce3-0bd1-44f3-9034-be9f241b888a)
Visit node 4 Visit node 4

Step 6: Now, Node 3 at the top of the stack, so visit node 3 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack
![277147623-3b88f04a-7846-4f75-89b4-22bbd5b48e52](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/9139080d-6514-47d6-a7dd-ffd84ba1d69b)
Visit node 3 Visit node 3

Now, the Stack becomes empty, which means we have visited all the nodes, and our DFS traversal ends.
## Algorithm:
1. Construct a Graph with Nodes and Edges
2. Depth First Search Uses Stack and Recursion
3. Insert a START node to the STACK
4. Find its Successors Or neighbors and Check whether the node is visited or not
5. If Not Visited, add it to the STACK. Else Call The Function Again Until No more nodes needs to be visited.
## PROGRAM
```
#import defaultdict
from collections import defaultdict
def dfs(graph,start,visited,path):
    path.append(start)
    visited[start]=True
    for neighbour in graph[start]:
        if visited[neighbour]==False:
            dfs(graph,neighbour,visited,path)
            visited[neighbour]=True
    return path
graph=defaultdict(list)
n,e=map(int,input().split())
for i in range(e):
    u,v=map(str,input().split())
    graph[u].append(v)
    graph[v].append(u)
#print(graph)
start='A'
visited=defaultdict(bool)
path=[]
traversedpath=dfs(graph,start,visited,path)
print(traversedpath)
```
## Output :
![image](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/0808e647-1b54-4dc5-ba5d-628bc5aa6fcc)
## Result:
Thus,a Graph was constructed and implementation of Depth First Search for the same graph was done successfully.

# ExpNo 2 : Implement Breadth First Search Traversal of a Graph
### Name : VIDYA NEELA M
### Register No : 212221230120
### Aim:
To Implement Breadth First Search Traversal of a Graph using Python 3.

### Theory:
Breadth-First Traversal (or Search) for a graph is like the Breadth-First Traversal of a tree. The only catch here is that, unlike trees, graphs may contain cycles so that we may come to the same node again. To avoid processing a node more than once, we divide the vertices into two categories:

1. Visited
2. Not Visited
A Boolean visited array is used to mark the visited vertices. For simplicity, it is assumed that all vertices are reachable from the starting vertex. BFS uses a queue data structure for traversal.

### How does BFS work?
Starting from the root, all the nodes at a particular level are visited first, and then the next level nodes are traversed until all the nodes are visited. To do this, a queue is used. All the adjacent unvisited nodes of the current level are pushed into the queue, and the current-level nodes are marked visited and popped from the queue. Illustration: Let us understand the working of the algorithm with the help of the following example. Step1: Initially queue and visited arrays are empty.

![278584708-dfa18c8b-fd94-4e34-a047-39606c532862](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/ff461914-08d4-4eaf-99aa-2972bdf3d389)
Queue and visited arrays are empty initially. Step2: Push node 0 into queue and mark it visited.

![278584702-b51a83b2-10b6-4480-8657-428918ea2a60](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/9f6d3599-709c-4be8-a830-8868154f5ec8)

Push node 0 into queue and mark it visited. Step 3: Remove node 0 from the front of queue and visit the unvisited neighbours and push them into queue.

![278584701-804b554a-f54f-4a3f-9424-855de0b3627f](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/12937fdd-81d9-4104-bf76-beea831d28e2)
Step 4: Remove node 1 from the front of queue and visit the unvisited neighbours and push them into queue.
![278584698-ac08a2a5-0020-4c52-941d-0600873fe911](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/a3540714-ec1b-4d91-a113-29d119fa87c3)
Step 5: Remove node 2 from the front of queue and visit the unvisited neighbours and push them into queue.
![278584693-07620032-42c7-49bb-8734-e8d721a77404](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/88fd7aa3-1094-43d9-9919-4e79761a30a1)
Step 6: Remove node 3 from the front of queue and visit the unvisited neighbours and push them into queue. As we can see that every neighbours of node 3 is visited, so move to the next node that are in the front of the queue.
![278584689-33b23be7-1296-4fe9-89bc-e2a309c7ddb8](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/c077dcea-91d0-4829-9e84-5c8b35544bef)

Steps 7: Remove node 4 from the front of queue and visit the unvisited neighbours and push them into queue. As we can see that every neighbours of node 4 are visited, so move to the next node that is in the front of the queue.

![278584680-edb350f4-a608-45e7-9043-8091360ffea5](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/70d06de9-401f-4803-b7d0-809d8eb30823)
Remove node 4 from the front of queue and visit the unvisited neighbours and push them into queue. Now, Queue becomes empty, So, terminate these process of iteration.
### Algorithm:
1. Construct a Graph with Nodes and Edges
2. Breadth First Uses Queue and iterates through the Queue for Traversal.
3. Insert a Start Node into the Queue.
4. Find its Successors Or neighbors and Check whether the node is visited or not.
5. If Not Visited, add it to the Queue. Else Continue.
6. Iterate steps 4 and 5 until all nodes get visited, and there are no more unvisited nodes.
### Program :
```
from collections import deque
from collections import defaultdict

def bfs(graph,start,visited,path):
    queue = deque()
    path.append(start)
    queue.append(start)
    visited[start] = True
    while len(queue) != 0:
        tmpnode = queue.popleft()
        for neighbour in graph[tmpnode]:
            if visited[neighbour] == False:
                path.append(neighbour)
                queue.append(neighbour)
                visited[neighbour] = True
    return path

graph = defaultdict(list)
v,e = map(int,input().split())
for i in range(e):
    u,v = map(str,input().split())
    graph[u].append(v)
    graph[v].append(u)

start = 'A'
path = []
visited = defaultdict(bool)
traversedpath = bfs(graph,start,visited,path)
print(traversedpath)
```
### OUTPUT
![278592482-f200bb32-807b-43f7-99f0-d0af14a52874](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/0c83aea9-3dfc-4719-a6f9-eaebd62283a6)

### RESULT
Thus,a Graph was constructed and implementation of Breadth First Search for the same graph was done successfully.

# ExpNo 3 : Implement A* search algorithm for a Graph
#### Name: VIDYA NEELA M
#### Register Number:212221230120
### Aim:
To ImplementA * Search algorithm for a Graph using Python 3.

### Algorithm:
// A* Search Algorithm 
1. Initialize the open list
2. Initialize the closed list put the starting node on the open list (you can leave its f at zero)
3. while the open list is not empty 
a) find the node with the least f on the open list, call it "q"

b) pop q off the open list

c) generate q's 8 successors and set their parents to q

d) for each successor
```
i) if successor is the goal, stop search

ii) else, compute both g and h for successor
  successor.g = q.g + distance between 
                      successor and q
  successor.h = distance from goal to 
  successor (This can be done using many 
  ways, we will discuss three heuristics- 
  Manhattan, Diagonal and Euclidean 
  Heuristics)
  
  successor.f = successor.g + successor.h

iii) if a node with the same position as 
    successor is in the OPEN list which has a 
   lower f than successor, skip this successor

iV) if a node with the same position as 
    successor  is in the CLOSED list which has
    a lower f than successor, skip this successor
    otherwise, add  the node to the open list
```
 end (for loop)

e) push q on the closed list end (while loop)   

### Sample Graph 
![277151990-b1377c3f-011a-4c0f-a843-516842ae056a](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/fa08f9db-fd61-467b-8dd2-ef08aa503227)
### PROGRAM:
```
from collections import defaultdict
H_dist ={}
def aStarAlgo(start_node, stop_node):
    open_set = set(start_node)
    closed_set = set()
    g = {}               #store distance from starting node
    parents = {}         # parents contains an adjacency map of all nodes
    #distance of starting node from itself is zero
    g[start_node] = 0
    #start_node is root node i.e it has no parent nodes
    #so start_node is set to its own parent node
    parents[start_node] = start_node
    while len(open_set) > 0:
        n = None
        #node with lowest f() is found
        for v in open_set:
            if n == None or g[v] + heuristic(v) < g[n] + heuristic(n):
                n = v
        if n == stop_node or Graph_nodes[n] == None:
            pass
        else:
            for (m, weight) in get_neighbors(n):
                #nodes 'm' not in first and last set are added to first
                #n is set its parent
                if m not in open_set and m not in closed_set:
                    open_set.add(m)
                    parents[m] = n
                    g[m] = g[n] + weight
                #for each node m,compare its distance from start i.e g(m) to the
                #from start through n node
                else:
                    if g[m] > g[n] + weight:
                        #update g(m)
                        g[m] = g[n] + weight
                        #change parent of m to n
                        parents[m] = n
                        #if m in closed set,remove and add to open
                        if m in closed_set:
                            closed_set.remove(m)
                            open_set.add(m)
        if n == None:
            print('Path does not exist!')
            return None
        
        # if the current node is the stop_node
        # then we begin reconstructin the path from it to the start_node
        if n == stop_node:
            path = []
            while parents[n] != n:
                path.append(n)
                n = parents[n]
            path.append(start_node)
            path.reverse()
            print('Path found: {}'.format(path))
            return path
        # remove n from the open_list, and add it to closed_list
        # because all of his neighbors were inspected
        open_set.remove(n)
        closed_set.add(n)
    print('Path does not exist!')
    return None

#define fuction to return neighbor and its distance
#from the passed node
def get_neighbors(v):
    if v in Graph_nodes:
        return Graph_nodes[v]
    else:
        return None
def heuristic(n):
    return H_dist[n]

graph = defaultdict(list)
n,e = map(int,input().split())
for i in range(e):
    u,v,cost = map(str,input().split())
    t=(v,float(cost))
    graph[u].append(t)
    t1=(u,float(cost))
    graph[v].append(t1)
for i in range(n):
    node,h=map(str,input().split())
    H_dist[node]=float(h)
print(H_dist)

   
Graph_nodes=graph
print(graph)
aStarAlgo('A', 'J')
```
### OUTPUT
![image](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/c37188be-f3f4-42b9-ac7c-accf9e033db2)
### RESULT
Thus the implementation of A* Search algorithm is done successfully.
# ExpNo 4 : Implement Simple Hill Climbing Algorithm
#### Name: VIDYA NEELA M
#### Register Number:212221230120
### Aim:
Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration

### Theory: 
Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space. Feedback is provided in terms of heuristic function

### Algorithm:
1. Evaluate the initial state.If it is a goal state then return it and quit. Otherwise, continue with initial state as current state.
2. Loop until a solution is found or there are no new operators left to be applied in current state:
    * Select an operator that has not yet been applied to the current state and apply it to produce a new state
* Evaluate the new state:
* if it is a goal state, then return it and quit
* if it is not a goal state but better than current state then make new state as current state
* if it is not better than current state then continue in the loop
### Steps Applied:
### Step-1
Generate Random String of the length equal to the given String

### Step-2
Mutate the randomized string each character at a time

### Step-3
Evaluate the fitness function or Heuristic Function

### Step-4:
Lopp Step -2 and Step-3 until we achieve the score to be Zero to achieve Global Minima.

### Program :
```
import random
import string
def generate_random_solution(answer):
    l=len(answer)
    return [random.choice(string.printable) for _ in range(l)]
def evaluate(solution,answer):
    print(solution)
    target=list(answer)
    diff=0
    for i in range(len(target)):
        s=solution[i]
        t=target[i]
        diff +=abs(ord(s)-ord(t))
    return diff
def mutate_solution(solution):
    ind=random.randint(0,len(solution)-1)
    solution[ind]=random.choice(string.printable)
    return solution
def SimpleHillClimbing():
    answer="Artificial Intelligence"
    best=generate_random_solution(answer)
    best_score=evaluate(best,answer)
    while True:
        print("Score:",best_score," Solution : ","".join(best))  
        if best_score==0:
            break
        new_solution=mutate_solution(list(best))
        score=evaluate(new_solution,answer)   
        if score<best_score:
            best=new_solution
            best_score=score
#answer="Artificial Intelligence"
#print(generate_random_solution(answer))
#solution=generate_random_solution(answer)
#print(evaluate(solution,answer))
SimpleHillClimbing()
```
### OUTPUT
![image](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/f5a32dd5-2ba5-4cc3-aaa5-1986b129fafd)
### RESULT
Thus the Implementation of Simple Hill Climbing Algorithm and Generating a String by Mutating a Single Character at each iteration is done successfully.

# ExpNo 5 : Implement Minimax Search Algorithm for a Simple TIC-TAC-TOE game
#### Name : VIDYA NEELA M
#### Register No : 212221230120
### Aim:
Implement Minimax Search Algorithm for a Simple TIC-TAC-TOE game

### Theory and Procedure:
To begin, let's start by defining what it means to play a perfect game of tic tac toe:

If I play perfectly, every time I play I will either win the game, or I will draw the game. Furthermore if I play against another perfect player, I will always draw the game.

How might we describe these situations quantitatively? Let's assign a score to the "end game conditions:"

I win, hurray! I get 10 points! I lose, shit. I lose 10 points (because the other player gets 10 points) I draw, whatever. I get zero points, nobody gets any points. So now we have a situation where we can determine a possible score for any game end state.

Looking at a Brief Example To apply this, let's take an example from near the end of a game, where it is my turn. I am X. My goal here, obviously, is to maximize my end game score.
![278596374-09944f56-1860-451b-a475-c769ab70e5df](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/767c7e4f-bd22-4f82-ab76-91951e70cd97)
If the top of this image represents the state of the game I see when it is my turn, then I have some choices to make, there are three places I can play, one of which clearly results in me wining and earning the 10 points. If I don't make that move, O could very easily win. And I don't want O to win, so my goal here, as the first player, should be to pick the maximum scoring move.

But What About O? What do we know about O? Well we should assume that O is also playing to win this game, but relative to us, the first player, O wants obviously wants to chose the move that results in the worst score for us, it wants to pick a move that would minimize our ultimate score. Let's look at things from O's perspective, starting with the two other game states from above in which we don't immediately win: 2

![278596423-3e5dcbfd-5e83-4406-ba1c-8c2d1ffdfcbb](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/2ae7afc2-a328-4a74-a77f-36ccb7f640ee)

The choice is clear, O would pick any of the moves that result in a score of -10.

Describing Minimax The key to the Minimax algorithm is a back and forth between the two players, where the player whose "turn it is" desires to pick the move with the maximum score. In turn, the scores for each of the available moves are determined by the opposing player deciding which of its available moves has the minimum score. And the scores for the opposing players moves are again determined by the turn-taking player trying to maximize its score and so on all the way down the move tree to an end state.

A description for the algorithm, assuming X is the "turn taking player," would look something like:

If the game is over, return the score from X's perspective. Otherwise get a list of new game states for every possible move Create a scores list For each of these states add the minimax result of that state to the scores list If it's X's turn, return the maximum score from the scores list If it's O's turn, return the minimum score from the scores list You'll notice that this algorithm is recursive, it flips back and forth between the players until a final score is found.
![278596500-c8eb6f56-e070-4c76-80ae-78d3c54f86a5](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/201830b0-cf89-4bba-9894-2218880d8536)
It's X's turn in state 1. X generates the states 2, 3, and 4 and calls minimax on those states.

State 2 pushes the score of +10 to state 1's score list, because the game is in an end state.

State 3 and 4 are not in end states, so 3 generates states 5 and 6 and calls minimax on them, while state 4 generates states 7 and 8 and calls minimax on them.

State 5 pushes a score of -10 onto state 3's score list, while the same happens for state 7 which pushes a score of -10 onto state 4's score list.

State 6 and 8 generate the only available moves, which are end states, and so both of them add the score of +10 to the move lists of states 3 and 4.

Because it is O's turn in both state 3 and 4, O will seek to find the minimum score, and given the choice between -10 and +10, both states 3 and 4 will yield -10.

Finally the score list for states 2, 3, and 4 are populated with +10, -10 and -10 respectively, and state 1 seeking to maximize the score will chose the winning move with score +10, state 2.

##A Coded Version of Minimax Hopefully by now you have a rough sense of how th e minimax algorithm determines the best move to play. Let's examine my implementation of the algorithm to solidify the understanding:

Here is the function for scoring the game:

### @player is the turn taking player
def score(game) if game.win?(@player) return 10 elsif game.win?(@opponent) return -10 else return 0 end end Simple enough, return +10 if the current player wins the game, -10 if the other player wins and 0 for a draw. You will note that who the player is doesn't matter. X or O is irrelevant, only who's turn it happens to be.

And now the actual minimax algorithm; note that in this implementation a choice or move is simply a row / column address on the board, for example [0,2] is the top right square on a 3x3 board.

def minimax(game) return score(game) if game.over? scores = [] # an array of scores moves = [] # an array of moves
```
# Populate the scores array, recursing as needed
game.get_available_moves.each do |move|
    possible_game = game.get_new_state(move)
    scores.push minimax(possible_game)
    moves.push move
end

# Do the min or the max calculation
if game.active_turn == @player
    # This is the max calculation
    max_score_index = scores.each_with_index.max[1]
    @choice = moves[max_score_index]
    return scores[max_score_index]
else
    # This is the min calculation
    min_score_index = scores.each_with_index.min[1]
    @choice = moves[min_score_index]
    return scores[min_score_index]
end
```
### PROGRAM :
```
import time

class Game:
    def __init__(self):
        self.initialize_game()

    def initialize_game(self):
        self.current_state = [['.','.','.'],
                              ['.','.','.'],
                              ['.','.','.']]

        # Player X always plays first
        self.player_turn = 'X'

    def draw_board(self):
        for i in range(0, 3):
            for j in range(0, 3):
                print('{}|'.format(self.current_state[i][j]), end=" ")
            print()
        print()
    def is_valid(self, px, py):
        if px < 0 or px > 2 or py < 0 or py > 2:
            return False
        elif self.current_state[px][py] != '.':
            return False
        else:
            return True
    def is_end(self):
    # Vertical win
        for i in range(0, 3):
            if (self.current_state[0][i] != '.' and
                self.current_state[0][i] == self.current_state[1][i] and
                self.current_state[1][i] == self.current_state[2][i]):
                return self.current_state[0][i]

        # Horizontal win
        for i in range(0, 3):
            if (self.current_state[i] == ['X', 'X', 'X']):
                return 'X'
            elif (self.current_state[i] == ['O', 'O', 'O']):
                return 'O'

    # Main diagonal win
        if (self.current_state[0][0] != '.' and
            self.current_state[0][0] == self.current_state[1][1] and
            self.current_state[0][0] == self.current_state[2][2]):
            return self.current_state[0][0]

    # Second diagonal win
        if (self.current_state[0][2] != '.' and
            self.current_state[0][2] == self.current_state[1][1] and
            self.current_state[0][2] == self.current_state[2][0]):
            return self.current_state[0][2]

    # Is the whole board full?
        for i in range(0, 3):
            for j in range(0, 3):
            # There's an empty field, we continue the game
                if (self.current_state[i][j] == '.'):
                    return None

    # It's a tie!
        return '.'
    def max(self):

        # Possible values for maxv are:
        # -1 - loss
        # 0  - a tie
        # 1  - win

        # We're initially setting it to -2 as worse than the worst case:
        maxv = -2

        px = None
        py = None

        result = self.is_end()

        # If the game came to an end, the function needs to return
        # the evaluation function of the end. That can be:
        # -1 - loss
        # 0  - a tie
        # 1  - win
        if result == 'X':
            return (-1, 0, 0)
        elif result == 'O':
            return (1, 0, 0)
        elif result == '.':
            return (0, 0, 0)

        for i in range(0, 3):
            for j in range(0, 3):
                if self.current_state[i][j] == '.':
                    # On the empty field player 'O' makes a move and calls Min
                    # That's one branch of the game tree.
                    self.current_state[i][j] = 'O'
                    (m, min_i, min_j) = self.min()
                    # Fixing the maxv value if needed
                    if m > maxv:
                        maxv = m
                        px = i
                        py = j
                    # Setting back the field to empty
                    self.current_state[i][j] = '.'
        return (maxv, px, py)

    def min(self):

        # Possible values for minv are:
        # -1 - win
        # 0  - a tie
        # 1  - loss

        # We're initially setting it to 2 as worse than the worst case:
        minv = 2

        qx = None
        qy = None

        result = self.is_end()

        if result == 'X':
            return (-1, 0, 0)
        elif result == 'O':
            return (1, 0, 0)
        elif result == '.':
            return (0, 0, 0)

        for i in range(0, 3):
            for j in range(0, 3):
                if self.current_state[i][j] == '.':
                    self.current_state[i][j] = 'X'
                    (m, max_i, max_j) = self.max()
                    if m < minv:
                        minv = m
                        qx = i
                        qy = j
                    self.current_state[i][j] = '.'

        return (minv, qx, qy)
    def play(self):
        while True:
            self.draw_board()
            self.result = self.is_end()

            # Printing the appropriate message if the game has ended
            if self.result != None:
                if self.result == 'X':
                    print('The winner is X!')
                elif self.result == 'O':
                    print('The winner is O!')
                elif self.result == '.':
                    print("It's a tie!")

                self.initialize_game()
                return

            # If it's player's turn
            if self.player_turn == 'X':

                while True:

                    start = time.time()
                    (m, qx, qy) = self.min()
                    end = time.time()
                    print('Evaluation time: {}s'.format(round(end - start, 7)))
                    print('Recommended move: X = {}, Y = {}'.format(qx, qy))

                    px = int(input('Insert the X coordinate: '))
                    py = int(input('Insert the Y coordinate: '))

                    (qx, qy) = (px, py)

                    if self.is_valid(px, py):
                        self.current_state[px][py] = 'X'
                        self.player_turn = 'O'
                        break
                    else:
                        print('The move is not valid! Try again.')

            # If it's AI's turn
            else:
                (m, px, py) = self.max()
                self.current_state[px][py] = 'O'
                self.player_turn = 'X'
def main():
    g = Game()
    g.play()

if __name__ == "__main__":
    main()
```
### OUTPUT:
![278601563-04a6e1b2-c9a2-4d06-b330-43bbd054df26](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/c810ff76-f4f5-4d07-822d-5509923de442)
![278601556-067f8e55-2e4f-48e6-bf13-dcaf01e32b63](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/197ff1be-552e-4a83-9c27-50f887801a52)


### RESULT:
Thus,Implementation of Minimax Search Algorithm for a Simple TIC-TAC-TOE game wasa done successfully.

# ExpNo 6 : Implement Alpha-beta pruning of Minimax Search Algorithm for a Simple TIC-TAC-TOE game</h1> 
#### Name: VIDYA NEELA M
#### Register Number: 212221230120
## Aim:

Implement Alpha-beta pruning of Minimax Search Algorithm for a Simple TIC-TAC-TOE game

<h1>GOALS of Alpha-Beta Pruning in MiniMax Search Algorithm</h1>

<h3>Improve the decision-making efficiency of the computer player by reducing the number of evaluated nodes in the game tree.</h3>
<h3>Tic-Tac-Toe game implementation incorporating the Alpha-Beta pruning and the Minimax algorithm with Python Code.</h3>
<h1>IMPLEMENTATION</h1>

The project involves developing a Tic-Tac-Toe game implementation incorporating the Alpha-Beta pruning with the Minimax algorithm. Using this algorithm, the computer player analyzes the game state, evaluates possible moves, and selects the optimal action based on the anticipated outcomes.

<h1>The Minimax algorithm</h1>

recursively evaluates all possible moves and their potential outcomes, creating a game tree.

<h1>Alpha-Beta pruning</h1>

Alpha–Beta (𝛼−𝛽) algorithm is actually an improved minimax using a heuristic. It stops evaluating a move when it makes sure that it’s worse than a previously examined move. Such moves need not to be evaluated further.

When added to a simple minimax algorithm, it gives the same output but cuts off certain branches that can’t possibly affect the final decision — dramatically improving the performance
<hr>

### PROGRAM:
```
import time

class Game:
    def __init__(self):
        self.initialize_game()

    def initialize_game(self):
        self.current_state = [['.','.','.'],
                              ['.','.','.'],
                              ['.','.','.']]

        # Player X always plays first
        self.player_turn = 'X'

    def draw_board(self):
        for i in range(0, 3):
            for j in range(0, 3):
                print('{}|'.format(self.current_state[i][j]), end=" ")
            print()
        print()
    def is_valid(self, px, py):
        if px < 0 or px > 2 or py < 0 or py > 2:
            return False
        elif self.current_state[px][py] != '.':
            return False
        else:
            return True
    def is_end(self):
    # Vertical win
        for i in range(0, 3):
            if (self.current_state[0][i] != '.' and
                self.current_state[0][i] == self.current_state[1][i] and
                self.current_state[1][i] == self.current_state[2][i]):
                return self.current_state[0][i]

        # Horizontal win
        for i in range(0, 3):
            if (self.current_state[i] == ['X', 'X', 'X']):
                return 'X'
            elif (self.current_state[i] == ['O', 'O', 'O']):
                return 'O'

    # Main diagonal win
        if (self.current_state[0][0] != '.' and
            self.current_state[0][0] == self.current_state[1][1] and
            self.current_state[0][0] == self.current_state[2][2]):
            return self.current_state[0][0]

    # Second diagonal win
        if (self.current_state[0][2] != '.' and
            self.current_state[0][2] == self.current_state[1][1] and
            self.current_state[0][2] == self.current_state[2][0]):
            return self.current_state[0][2]

    # Is the whole board full?
        for i in range(0, 3):
            for j in range(0, 3):
            # There's an empty field, we continue the game
                if (self.current_state[i][j] == '.'):
                    return None

    # It's a tie!
        return '.'
    def max_alpha_beta(self, alpha, beta):
        maxv = -2
        px = None
        py = None

        result = self.is_end()

        if result == 'X':
            return (-1, 0, 0)
        elif result == 'O':
            return (1, 0, 0)
        elif result == '.':
            return (0, 0, 0)

        for i in range(0, 3):
            for j in range(0, 3):
                if self.current_state[i][j] == '.':
                    self.current_state[i][j] = 'O'
                    (m, min_i, in_j) = self.min_alpha_beta(alpha, beta)
                    if m > maxv:
                        maxv = m
                        px = i
                        py = j
                    self.current_state[i][j] = '.'

                    # Next two ifs in Max and Min are the only difference between regular algorithm and minimax
                    if maxv >= beta:
                        return (maxv, px, py)

                    if maxv > alpha:
                        alpha = maxv

        return (maxv, px, py)

    def min_alpha_beta(self, alpha, beta):

        minv = 2

        qx = None
        qy = None

        result = self.is_end()

        if result == 'X':
            return (-1, 0, 0)
        elif result == 'O':
            return (1, 0, 0)
        elif result == '.':
            return (0, 0, 0)

        for i in range(0, 3):
            for j in range(0, 3):
                if self.current_state[i][j] == '.':
                    self.current_state[i][j] = 'X'
                    (m, max_i, max_j) = self.max_alpha_beta(alpha, beta)
                    if m < minv:
                        minv = m
                        qx = i
                        qy = j
                    self.current_state[i][j] = '.'

                    if minv <= alpha:
                        return (minv, qx, qy)

                    if minv < beta:
                        beta = minv

        return (minv, qx, qy)
    def play_alpha_beta(self):
        while True:
            self.draw_board()
            self.result = self.is_end()

            if self.result != None:
                if self.result == 'X':
                    print('The winner is X!')
                elif self.result == 'O':
                    print('The winner is O!')
                elif self.result == '.':
                    print("It's a tie!")


                self.initialize_game()
                return

            if self.player_turn == 'X':

                while True:
                    start = time.time()
                    (m, qx, qy) = self.min_alpha_beta(-2, 2)
                    end = time.time()
                    print('Evaluation time: {}s'.format(round(end - start, 7)))
                    print('Recommended move: X = {}, Y = {}'.format(qx, qy))

                    px = int(input('Insert the X coordinate: '))
                    py = int(input('Insert the Y coordinate: '))

                    qx = px
                    qy = py

                    if self.is_valid(px, py):
                        self.current_state[px][py] = 'X'
                        self.player_turn = 'O'
                        break
                    else:
                        print('The move is not valid! Try again.')

            else:
                (m, px, py) = self.max_alpha_beta(-2, 2)
                self.current_state[px][py] = 'O'
                self.player_turn = 'X'
def main():
    g = Game()
    g.play_alpha_beta()

if __name__ == "__main__":
    main()
```
### Output :
![278600639-63df3aa2-582a-41ba-b9b4-2f743280fd17](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/5d75fcaf-09b8-4fff-ad07-61091705c34b)

![278600632-1e09dd09-50c7-45c5-b7f8-fabf1e803aea](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/4d059d58-b877-404c-82eb-43fc0bb8200b)
### Result :
Thus the Implementation of Alpha-beta pruning of Minimax Search Algorithm for a Simple TIC-TAC-TOE game is done successfully

<h1>ExpNo 7 : Solve Cryptarithmetic Problem,a CSP(Constraint Satisfaction Problem) using Python</h1> 
<h3>Name: VIDYA NEELA M</h3>
<h3>Register Number:212221230120</h3>
<H3>Aim:</H3>
<p>
    To solve Cryptarithmetic Problem,a CSP(Constraint Satisfaction Problem) using Python
</p>
<h3>Procedure:</h3>
Input and Output
<br>Input:
This algorithm will take three words.
<br> B A S E<br>
    B A L L<br>
           ----------<br>
           G A M E S<br>

Output:
It will show which letter holds which number from 0 – 9.
For this case it is like this.

              B A S E                         2 4 6 1
              B A L L                         2 4 5 5
             ---------                       ---------
            G A M E S                       0 4 9 1 6
Algorithm
For this problem, we will define a node, which contains a letter and its corresponding values.<br>

isValid(nodeList, count, word1, word2, word3)<br>

Input − A list of nodes, the number of elements in the node list and three words.<br>

Output − True if the sum of the value for word1 and word2 is same as word3 value.<br>

Begin<br>
   m := 1<br>
   for each letter i from right to left of word1, do<br>
      ch := word1[i]<br>
      for all elements j in the nodeList, do<br>
         if nodeList[j].letter = ch, then<br>
            break<br>
      done<br>
      val1 := val1 + (m * nodeList[j].value)<br>
      m := m * 10<br>
   done<br>

   m := 1<br>
   for each letter i from right to left of word2, do<br>
      ch := word2[i]<br>
      for all elements j in the nodeList, do<br>
         if nodeList[j].letter = ch, then<br>
            break<br>
      done<br>

      val2 := val2 + (m * nodeList[j].value)
      m := m * 10
   done<br>

   m := 1<br>
   for each letter i from right to left of word3, do<br>
      ch := word3[i]<br>
      for all elements j in the nodeList, do<br>
         if nodeList[j].letter = ch, then<br>
            break<br>
      done<br>

      val3 := val3 + (m * nodeList[j].value)
      m := m * 10
   done<br>

   if val3 = (val1 + val2), then<br>
      return true<br>
   return false<br>
End<br>
<hr>

### PROGRAM:

```
from itertools import permutations

def solve_cryptarithmetic():
    for perm in permutations(range(10), 8):
        S, E, N, D, M, O, R, Y = perm

        # Check for leading zeros
        if S == 0 or M == 0:
            continue

        # Check the equation constraints
        SEND = 1000 * S + 100 * E + 10 * N + D
        MORE = 1000 * M + 100 * O + 10 * R + E
        MONEY = 10000 * M + 1000 * O + 100 * N + 10 * E + Y

        if SEND + MORE == MONEY:
            return SEND, MORE, MONEY

    return None

solution = solve_cryptarithmetic()

if solution:
    SEND, MORE, MONEY = solution
    print(f'SEND = {SEND}')
    print(f'MORE = {MORE}')
    print(f'MONEY = {MONEY}')
else:
    print("No solution found.")
```
### OUTPUT
![278599904-5f879f45-a43f-46ac-9aed-d6b831869339](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/c7696fe7-9dba-47fe-9718-96d799bdfe9a)

### RESULT:
Thus a Cryptarithmetic Problem was solved using Python successfully

<h1>ExpNo 8 : Solve Wumpus World Problem using Python demonstrating Inferences from Propositional Logic</h1> 
<h3>Name: VIDYA NEELA M</h3>
<h3>Register Number:212221230120</h3>
<H3>Aim:</H3>
<p>
    To solve  Wumpus World Problem using Python demonstrating Inferences from Propositional Logic
</p>
<h1>Problem Description</h1>
<hr>
<h2>Wumpus World</h2>
<hr>
The Wumpus world is a simple world example to illustrate the worth of a knowledge-based agent and to represent knowledge representation.

The figure below shows a Wumpus world containing one pit and one Wumpus. There is an agent in room [1,1]. The goal of the agent is to exit the Wumpus world alive. The agent can exit the Wumpus world by reaching room [4,4]. The wumpus world contains exactly one Wumpus and one pit. There will be a breeze in the rooms adjacent to the pit, and there will be a stench in the rooms adjacent to Wumpus.

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/cd6b68dc-c79f-4dcb-8126-04da90d65912)

<center>Wumpus World Representation</center>
<p>
This is a python program that uses propositional logic sentences to check which rooms are safe. 

It is assumed that there will always be a safe path that the agent can take to exit the Wumpus world. The logical agent can take four actions: Up, Down, Left and Right. These actions help the agent move from one room to an adjacent room. The agent can perceive two things: Breeze and Stench.
</p>

<hr>

### program:
```
wumpus=[["Save","Breeze","PIT","Breeze"],
        ["Smell","Save","Breeze","Save"],
        ["WUMPUS","GOLD","PIT","Breeze"],
        ["Smell","Save","Breeze","PIT"]]
row=0
column=0
arrow=True
player=True
score=0
while(player):
    choice=input("press u to move up\npress d to move down\npress l to move left\npress r to move right\n")
    if choice == "u":
        if row != 0:
            row-=1
        else:
            print("move denied")
        
        print("current location: ",wumpus[row][column],"\n")
    elif choice == "d" :
        if row!=3:
            row+=1
        else:
            print("move denied")
        
        print("current location: ",wumpus[row][column],"\n")
    elif choice == "l" :
        if column!=0:
            column-=1
        else:
            print("move denied")
        
        print("current location: ",wumpus[row][column],"\n")
    elif choice == "r" :
        if column!=3:
            column+=1
        else:
            print("move denied")
        
        print("current location: ",wumpus[row][column],"\n")
    else:
        print("move denied")

    if wumpus[row][column]=="Smell" and arrow != False:
        arrow_choice=input("do you want to throw an arrow-->\npress y to throw\npress n to save your arrow\n")
        if arrow_choice == "y":
            arrow_throw=input("press u to throw up\npress d to throw down\npress l to throw left\npress r to throw right\n")
            if arrow_throw == "u":
                if wumpus[row-1][column] == "WUMPUS":
                    print("wumpus killed!")
                    score+=1000
                    print("score: ",score)
                    wumpus[row-1][column] = "Save"
                    wumpus[1][0]="Save"
                    wumpus[3][0]="Save"
                else:
                    print("arrow wasted...")
                    score-=10
                    print("score: ",score)
            elif arrow_throw == "d":
                if wumpus[row+1][column] == "WUMPUS":
                    print("wumpus killed!")
                    score+=1000
                    print("score: ",score)
                    wumpus[row+1][column] = "Save"
                    wumpus[1][0]="Save"
                    wumpus[3][0]="Save"
                else:
                    print("arrow wasted...")
                    score-=10
                    print("score: ",score)
            elif arrow_throw == "l":
                if wumpus[row][column-1] == "WUMPUS":
                    print("wumpus killed!")
                    score+=1000
                    print("score: ",score)
                    wumpus[row][column-1] = "Save"
                    wumpus[1][0]="Save"
                    wumpus[3][0]="Save"
                else:
                    print("arrow wasted...")
                    score-=10
                    print("score: ",score)
            elif arrow_throw == "r":
                if wumpus[row][column+1] == "WUMPUS":
                    print("wumpus killed!")
                    score+=1000
                    print("score: ",score)
                    wumpus[row][column+1] = "Save"
                    wumpus[1][0]="Save"
                    wumpus[3][0]="Save"
                else:
                    print("arrow wasted...")
                    score-=10
                    print("score: ",score)
                
            
            arrow=False
    if wumpus[row][column] == "WUMPUS" :
        score-=1000
        print("\nWumpus here!!\n You Die\nAnd your score is: ",score
              ,"\n")
        break
    if(wumpus[row][column]=='GOLD'):
        score+=1000
        print("GOLD FOUND!You won....\nYour score is: ",score,"\n")
        break
    if(wumpus[row][column]=='PIT'):
        score-=1000
        print("Ahhhhh!!!!\nYou fell in pit.\nAnd your score is: ",score,"\n")
        break
```
### OUTPUT:

![278599275-e9500f41-ea13-4888-b8e5-e2c9ceb80544](https://github.com/sithihajara/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94219582/0b216ce7-4a79-4f43-822a-fb1c48c333e0)

### Result :
Thus the Wumpus World Problem is solved using Python demonstrating Inferences from Propositional Logic successfully.
