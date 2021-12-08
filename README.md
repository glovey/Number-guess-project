# Number-guess-project
# my code for a 'guess the number' game
  
  import random
  
  record = []
  
  def score_check():
    if len(record) == 0:
      print ("there is no record, go get it tiger")
    else:  
      print (f"Ok, the record is {min(record)}, you got this!")  
  
  def new_game():
    name = input("Hello what's your name?")
    start = input(f"do you want to play a game {name}? Enter yes or no")
    attempts = 0
    rand = int(random.randint(1,10))
    score_check()
    while start.lower() == "yes":
      
      guess = int(input("Pick a number between 1 and 10")) 
      if guess < 1 or guess > 10:
          print ("Please pick a number between 1 and 10")
      elif guess == rand:
        attempts += 1
        print (f"well done you win, it took you {attempts} attempts")
        start = input(f"do you want to play again {name}?")
        record.append(attempts)
        print (record)
        attempts = 0
        score_check()
      elif guess < rand:
        print ("the number is higher!")
        attempts +=1
      elif guess > rand:
        print ("the number is lower!")
        attempts +=1
    else:
      if start.lower() == "no":
        print (f"ok no worries {name}, see you next time")
      else:
        start = input("that's not valid, please enter yes or no")
  new_game()        
