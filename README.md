# CountingSortAlgorithm 
def frequence(x):
    freq = [0] * (max(x) + 1)  # define the size of the list
    for i in x:
        freq[i] += 1
    return freq    

def CountSort(A):
    frq = frequence(A)
    B = [0] * len(A)
    for i in range(0, len(frq) - 1):
        frq[i + 1] = frq[i] + frq[i + 1]
        
    for i in range(len(A)):
        frq[A[i]] -= 1
        B[frq[A[i]]] = A[i]
    
    print(B)     

# Example usage
B = [1, 3, 2, 4, 3, 1]
CountSort(B)
