'''
Backtracking Algorithm to solve suduku puzzles
'''


''' The puzzle is stored as a list of list, each row is a list '''
puzzle = [
           [3,9,-1,-1,5,-1,-1,-1,-1],
           [-1,-1,-1,2,-1,-1,-1,-1,5],
           [-1,-1,-1,7,1,9,-1,8,-1],
           [-1,5,-1,-1,6,8,-1,-1,-1],
           [2,-1,6,-1,-1,3,-1,-1,-1],
           [-1,-1,-1,-1,-1,-1,-1,-1,4],
           [5,-1,-1,-1,-1,-1,-1,-1,-1],
           [6,7,-1,1,-1,5,-1,4,-1],
           [1,-1,9,-1,-1,-1,2,-1,-1]
                                       ]

def SolveSudukuPuzzle(puzzle):
    # Step 1: Find an empty cell so a guess can be made
    row, col = find_next_empty_cell(puzzle)
    
    if row is None:
        return True
    
    # Step 2: Place a guess starting from 1 up to 9
    for guess in range(1,10):
        # Check if the guess is valid      
        if(is_value_valid(puzzle,guess,row,col)):
            puzzle[row][col] = guess

            # Now need to recursivly call this function
            if SolveSudukuPuzzle(puzzle):
                return True
    
        # If guess is not valid or guess doesn't solve the puzzle, then
        # we are required to backtrack and try a new guess
        puzzle[row][col] = -1 #Resets our guess
        
    
    # If no guess works then the puzzle is unsolvable
    return False

def is_value_valid(puzzle,guess,row,col):
    
    # First Step: Check is guess is contained in the same row
    row_value = puzzle[row]
    if guess in row_value:
        return False
    
    # Second Step: Check if guess is contained in the same column
    for r in range(9):
        row_vals = puzzle[r]
        if(guess == row_vals[col]):
            return False
        
    # Third Step: Find th 3x3 grid the guess is in and compare the values
    row_start = (row // 3)*3 
    col_start = (col // 3 )*3
    print(row_start)
    print(col_start)
    for r in range(row_start,row_start+3):
        for c in range(col_start,col_start+3):
            if(puzzle[r][c]) == guess:
                return False        
    return True
    


def find_next_empty_cell(puzzle):
    
    #Search through the puzzle till is finds the first empty cell
    for row in range(len(puzzle)):
        for col in range(len(puzzle[row])):
            if(puzzle[row][col]==-1):
                return row,col 
            
    # Return None if there are no empty slots
    return None,None

SolveSudukuPuzzle(puzzle)
print(puzzle)
