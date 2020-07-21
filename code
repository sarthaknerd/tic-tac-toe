 #board
#display board
#playgame
#check win 
 #check rows
 #check columns
 #check diagonal 
#check tie
#check player
#flip player

#------GLOBAL VARIABLE-------


board = ["-","-","-",
         "-","-","-",
         "-","-","-"]


#if game still going       
game_is_still_going = True


#win/tie
winner =  None 


#turn
current_player = 'x'


#dispaly board
def display_board():
  print(board[0] + " | " + board[1] + " | " + board[2])
  print(board[3] + " | " + board[4] + " | " + board[5])
  print(board[6] + " | " + board[7] + " | " + board[8])

#play the game of tic tac toe 
def play_game():
  display_board() #display the board
  #keep loopping till game is over
  while game_is_still_going:

   
    #handle the turn from player 
    handle_turn(current_player)

    #check if game has ended 
    check_if_game_over()
    
    #flip the player
    flip_player()
  
  
  # the game has ended
  if winner == 'x' or winner == 'o':

     print('winner is' , winner )

  else:
      print('It is a Tie')
#handle a turn of an player 


def handle_turn(player):

  # Get position from player
  print(player + "'s turn.")
  position = input("Choose a position from 1-9: ")

  # Whatever the user inputs, make sure it is a valid input, and the spot is open
  valid = False
  while not valid:

    # Make sure the input is valid
    while position not in ["1", "2", "3", "4", "5", "6", "7", "8", "9"]:
      position = input("Choose a position from 1-9: ")
 
    # Get correct index in our board list
    position = int(position) - 1

    # Then also make sure the spot is available on the board
    if board[position] == "-":
      valid = True
    else:
      print("You can't go there. Go again.")

  # Put the game piece on the board
  board[position] = player

  # Show the game board
  display_board()



def check_if_game_over():
  check_for_win()
  check_for_tie()



def check_for_win():
  
  global winner 
   #check_rows
  row_winner = check_row()
  
  #check_columns 
  column_winner = check_column()
   #check_diagonal
  diagonal_winner = check_diagonal()

  if row_winner :
     #win
    winner = row_winner

  elif column_winner:
    
   #win
   winner = column_winner
  
  elif diagonal_winner:
     #win
     winner = diagonal_winner

  else:
    winner = None
    #no win

  return


# Check the rows for a win
def check_row():
  # Set global variables
  global game_is_still_going
  # Check if any of the rows have all the same value (and is not empty)
  row_1 = board[0] == board[1] == board[2] != "-"
  row_2 = board[3] == board[4] == board[5] != "-"
  row_3 = board[6] == board[7] == board[8] != "-"
  # If any row does have a match, flag that there is a win
  if row_1 or row_2 or row_3:
    game_is_still_going = False
  # Return the winner
  if row_1:
    return board[0] 
  elif row_2:
    return board[3] 
  elif row_3:
    return board[6] 
  # Or return None if there was no winner
  else:
    return None




def check_column():
  # Set global variables
  global game_is_still_going
  # Check if any of the columns have all the same value (and is not empty)
  column_1 = board[0] == board[3] == board[6] != "-"
  column_2 = board[1] == board[4] == board[7] != "-"
  column_3 = board[2] == board[5] == board[8] != "-"
  # If any row does have a match, flag that there is a win
  if column_1 or column_2 or column_3:
    game_is_still_going = False
  # Return the winner
  if column_1:
    return board[0] 
  elif column_2:
    return board[1] 
  elif column_3:
    return board[2] 
  # Or return None if there was no winner
  else:
    return None
  
  return


def check_diagonal():
  # Set global variables
  global game_is_still_going
  # Check if any of the columns have all the same value (and is not empty)
  diagonal_1 = board[0] == board[4] == board[8] != "-"
  diagonal_2 = board[2] == board[4] == board[6] != "-"
  # If any row does have a match, flag that there is a win
  if diagonal_1 or diagonal_2:
    game_is_still_going = False
  # Return the winner
  if diagonal_1:
    return board[0] 
  elif diagonal_2:
    return board[2]
  # Or return None if there was no winner
  else:
    return None
  return()

  


def check_for_tie():
  global game_is_still_going
  if "-"  not in  board:
     game_is_still_going = False
  return



def flip_player():
  global current_player
  if current_player == "x" :
    current_player = "o"
  elif current_player == "o":
    current_player = "x"
play_game()
