# IP Address Access Control Management using Python

## Project Overview
In this project, the task involves managing employee access to restricted
content at a healthcare company, specifically focusing on sensitive patient records. Access to these records is controlled through an allow list, which contains the IP addresses of employees permitted to sign into a restricted subnetwork. A remove list is also maintained, which identifies the employees or IP addresses that should be removed from the allow list.

An algorithm is required to be developed using Python code to automate this process. The algorithm will check whether any IP addresses on the remove list are still present in the allow list. If such addresses are found, they will be removed from the allow list file, ensuring that only authorized individuals retain access to the restricted subnetwork, thus enhancing security and compliance.

## Automating the task using function
```python
# Define a function named `update_file` that takes in two parameters: `import_file` and `remove_list`
# and combines the steps you've written in this lab leading up to this

def update_file(import_file, remove_list):

  # Build `with` statement to read in the initial contents of the file

  with open(import_file, "r") as file:

    # Use `.read()` to read the imported file and store it in a variable named `ip_addresses`

    ip_addresses = file.read()

  # Use `.split()` to convert `ip_addresses` from a string to a list

  ip_addresses = ip_addresses.split()

  # Build iterative statement
  # Name loop variable `element`
  # Loop through `ip_addresses`

  for element in ip_addresses:
    
    # Build conditional statement
    # If current element is in `remove_list`,
    
    if element in remove_list:

      # then current element should be removed from `ip_addresses`

      ip_addresses.remove(element)

  # Convert `ip_addresses` back to a string so that it can be written into the text file     

  ip_addresses = " ".join(ip_addresses)

  # Build `with` statement to rewrite the original file

  with open(import_file, "w") as file:

    # Rewrite the file, replacing its contents with `ip_addresses`

    file.write(ip_addresses)
```

### Summary & Steps
An algorithm was created to remove IP addresses identified in the `remove_list` variable from the "allow_list.txt" file of approved IP addresses. This algorithm involved opening the file, converting its contents into a string for reading, and then converting the string into a list stored in the variable `ip_addresses`. The IP addresses in `remove_list` were then iterated through, and during each iteration, the elements were evaluated to determine if they were part of the `ip_addresses` list. If an element was present, the `.remove()` method was applied to eliminate it from `ip_addresses`. Afterward, the `.join()` method was used to convert `ip_addresses` back into a string, enabling the revised list of IP addresses to overwrite the contents of the "allow_list.txt" file.
