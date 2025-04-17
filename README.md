# MushtaQAlgo
A completely randomized and recursive search algo [ACRRA]
import random

def optimized_random_search():
    """
    Optimized randomized search algorithm with memoization and limited attempts.
    """
    # Input the list of elements
    data = input("Enter the list of elements separated by spaces: ").split()
    
    # Input the target value to search for
    target = input("Enter the target value: ")

    if target not in data:
        return "Target not found."

    # Initialize variables
    visited_indices = set()
    attempts = 0
    max_attempts = 1000  # You can adjust this value as needed

    while attempts < max_attempts:
        attempts += 1
        
        # Randomly select an index
        random_index = random.randint(0, len(data) - 1)
        
        # Skip if the index has already been visited
        if random_index in visited_indices:
            continue

        # Mark the index as visited
        visited_indices.add(random_index)

        # Check if the selected element matches the target
        if data[random_index] == target:
            return f"Target found at index {random_index} after {attempts} attempts."

    # If max_attempts is reached without finding the target
    return "Target not found within the maximum number of attempts."

# Run the algorithm
print(optimized_random_search())
