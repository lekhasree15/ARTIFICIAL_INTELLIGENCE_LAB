import random

board = [" "] * 9

def display_board():
    print()
    print(f" {board[0]} | {board[1]} | {board[2]} ")
    print("---+---+---")
    print(f" {board[3]} | {board[4]} | {board[5]} ")
    print("---+---+---")
    print(f" {board[6]} | {board[7]} | {board[8]} ")
    print()

def check_winner(player):
    winning_positions = [
        (0, 1, 2),
        (3, 4, 5),
        (6, 7, 8),
        (0, 3, 6),
        (1, 4, 7),
        (2, 5, 8),
        (0, 4, 8),
        (2, 4, 6)
    ]

    for a, b, c in winning_positions:
        if board[a] == board[b] == board[c] == player:
            return True

    return False

def ai_move():
    empty_positions = [i for i in range(9) if board[i] == " "]

    for position in empty_positions:
        board[position] = "O"
        if check_winner("O"):
            return
        board[position] = " "

    for position in empty_positions:
        board[position] = "X"
        if check_winner("X"):
            board[position] = "O"
            return
        board[position] = " "

    position = random.choice(empty_positions)
    board[position] = "O"


print("=== TIC-TAC-TOE ===")
print("You are X")
print("AI is O")

for turn in range(9):

    display_board()

    while True:
        try:
            position = int(input("Enter your position (1-9): ")) - 1

            if position < 0 or position > 8:
                print("Please enter a number from 1 to 9.")
            elif board[position] != " ":
                print("That position is already occupied!")
            else:
                board[position] = "X"
                break

        except ValueError:
            print("Please enter a valid number.")

    if check_winner("X"):
        display_board()
        print(" You win!")
        break

    if " " not in board:
        display_board()
        print("It's a draw!")
        break

    print("AI is thinking...")
    ai_move()

    if check_winner("O"):
        display_board()
        print(" AI wins!")
        break

else:
    display_board()
