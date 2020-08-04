# SpiralMatrix
My attempt to fill a n x n matrix with numbers in a spiral order.

n = int(input())
m = [[0 for j in range(n)] for i in range(n)]

low, high = 0, n - 1 #defining borders of the matrix

for i in range(1, int((n + 1) / 2)):
    for j in range(low, high + 1): #upper left to upper right
        m[low][j] = value
        value += 1
    for j in range(low + 1, high + 1): #upper right to lower right
        m[j][high] = value
        value += 1
    for j in range(high - 1, low - 1, -1): #lower right to lower left
        m[high][j] = value
        value += 1
    for j in range(high - 1, low, - 1): #lower left to upper left
        m[j][low] = value
        value += 1
    low += 1 #when the loops are done, we increase the lowest border by 1 and descrease the highest accordingly so as to go inwards
    high -= 1

for i in range(len(m)): #when the filling is done, we are ready to print the final result
    for j in range(len(m)):
        print(m[i][j], end=' ')
    print()
