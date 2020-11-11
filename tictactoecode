#----- Global Variables ------

#board
board = ["-", "-", "-",
         "-", "-", "-",
         "-", "-", "-",]

#If game still game still going
game_still_going = True

#Who won? or tie?
winner = None

#Who's turn is it?
current_player = "X"


#----- Functions ------

#display board
def display_board():
    print(board[0] + " | " + board[1] + " | " + board[2])
    print(board[3] + " | " + board[4] + " | " + board[5])
    print(board[6] + " | " + board[7] + " | " + board[8])


#start the game
def play_game():

    #displaying the board
    display_board()

    while game_still_going:

        #current player taking there turn
        take_turn(current_player)

        #check is the game has ended
        check_game_over()

        #change to the other player
        flip_player()

    #who won
    if winner == "X" or winner == "O":
      print(winner + " is the winner!")
    elif winner == None:
      print("It's a tie!")



#take turn
def take_turn(player):
    
    #Display who's turn it is
    print(player + "'s turn.")

    #Ask the player to enter a position number 
    position = input("Choose a position from 1-9 ")

    #Checking if the inputted position is available 
    valid = False
    while not valid: 
      
      while position not in ["1", "2", "3", "4", "5", "6", "7", "8", "9"]:
        position = input("Please enter a valid number between 1-9: ")

      position = int(position) - 1

      if board[position] == "-":
        valid = True
      else:
        print("You can't go here, try again.")

    #Placing the position on the board
    board[position] = player

    display_board()


#-----Checking end game-----


#Check game is over 
def check_game_over():
    check_winner()
    check_tie()

def check_winner():

  #Global Variables
  global winner 

  #check rows
  row_winner = check_rows()
  #check comulmns
  coloumn_winner = check_columns()
  #check diagonals 
  diagonal_winner = check_diagonals()
  #check tie 
  its_tie = check_tie()

  
  if row_winner:
    winner = row_winner
  if coloumn_winner:
    winner = coloumn_winner
  if diagonal_winner:
    winner = diagonal_winner
  if its_tie:
    winner = None
  


def check_rows():
  #setting up of global vairiabls
  global game_still_going

  #Check if any of the rows have the same value (and is not empty)
  row_1 = board[0] == board[1] == board[2] != "-"
  row_2 = board[3] == board[4] == board[5] != "-"
  row_3 = board[6] == board[7] == board[8] != "-"
  
  #If any rows match, stop the game 
  if row_1 or row_2 or row_3:
    game_still_going = False
  
  #Return the winner
  if row_1:
    return board[0]
  elif row_2:
    return board[3]
  elif row_3:
    return board[6]
  return

def check_columns():
  #setting up of global vairiabls
  global game_still_going

  #check if any of the rows have the same value
  column_1 = board[0] == board[3] == board[6] != "-"
  column_2 = board[1] == board[4] == board[7] != "-"
  column_3 = board[2] == board[5] == board[8] != "-"

  #If any columns match, stop the game 
  if column_1 or column_2 or column_3:
    game_still_going = False
  
  #Return the winner
  if column_1:
    return board[0]
  elif column_2:
    return board[1]
  elif column_3:
    return board[2]


def check_diagonals():
  #setting up of global vairiabls
  global game_still_going

  #check any diagonals have the same value
  diagonal_1 = board[0] == board[4] == board[8] != "-"
  diagonal_2 = board[2] == board[4] == board[6] != "-"

  #If any diagonals match, stop the game 
  if diagonal_1 or diagonal_2:
    game_still_going = False
  
  #Return the winner
  if diagonal_1:
    return board[0]
  elif diagonal_2:
    return board[2]
  

def check_tie():
  #Global Variables
  global game_still_going
  #If a "-" is not in the board, then stop the game as it's a tie
  if "-" not in board:
    game_still_going = False

def flip_player():
  #global vairiabls
  global current_player

  #flipping of player X to O
  if current_player == "X":
    current_player = "O"
   #flipping of player O to X 
  elif current_player == "O":
    current_player = "X"



play_game()
