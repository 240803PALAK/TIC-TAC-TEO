
def board(x,y):
    print(f"{'X'if x[0] else ('O' if y[0] else 0)} | {'X'if x[1] else ('O' if y[1] else 1)} | {'X'if x[2] else ('O' if y[2] else 2)} ")
    print("--|---|---")
    print(f"{'X'if x[3] else ('O' if y[3] else 3)} | {'X'if x[4] else ('O' if y[4] else 4)} | {'X'if x[5] else ('O' if y[5] else 5)} ")
    print("--|---|---")
    print(f"{'X'if x[6] else ('O' if y[6] else 6)} | {'X'if x[7] else ('O' if y[7] else 7)} | {'X'if x[8] else ('O' if y[8] else 8)} ")

def sum(a,b,c):
    return a+b+c
def check(xState,zState):
    wins=[[0,1,2],[3,4,5],[6,7,8],[0,3,6],[1,4,7],[2,5,8],[0,4,5],[2,4,6]]
    for win in wins:
        if sum(xState[win[0]],xState[win[1]],xState[win[2]])==3:
            return 1
        if sum(zState[win[0]], zState[win[1]], zState[win[2]]) == 3:
            return 0
    return -1

if __name__=="__main__":
    print("=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-==== Tic Tac Toe ====-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=")
    player1=input("Enter the 1 Player Name : ")
    player2 =input("Enter the 2 Player Name : ")
    xState=[0,0,0,0,0,0,0,0,0,0]
    zState = [0, 0, 0, 0, 0, 0, 0, 0,0,0]
    turn=1 # 1 for X and 0 for O
    print("Welcome to Tic tac Toe")
    while(True):
        while(True):
            board(xState, zState)
            if (turn == 1):
                print(f"---------- {player1} Turn ----------")
                value = int(input("Please enter the value :"))
                if xState[value]==1 or zState[value]==1:
                    print("\nThe Value is already enter")
                    break
                xState[value] = 1
                turn = 0
            else:
                print(f"---------- {player2} Turn ----------")
                value = int(input("Please enter the value :"))
                if xState[value]==1 or zState[value]==1 :
                    print("\nThe Value is already enter")
                    break
                zState[value] = 1
                turn = 1
            cwin = check(xState, zState)
                   if (cwin != -1):
                print("---------------------------------------------- MATCH OVER ------------------------------------------------")
                board(xState, zState)
                if (cwin == 1):
                    print(f"\n\n============================ {player1} Won ===================")
                    exit()
                else:
                    print(f"\n\n============================ {player2} Won ===================")
                    exit()




