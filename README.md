# week4-assignmentFile Read & Write Challenge 🖋️: Create a program that reads a file and writes a modified version to a new file.
Error Handling Lab 🧪: Ask the user for a filename and handle errors if it doesn’t exist or can’t be read.
Here’s a solution for both tasks:

### **File Read & Write Challenge 🖋️:**
This program will read a file, modify its content (for example, converting it to uppercase), and then write the modified content to a new file.

```python
def modify_file(input_filename, output_filename):
    try:
        # Open the input file for reading
        with open(input_filename, 'r') as infile:
            content = infile.read()

        # Modify the content (for example, convert to uppercase)
        modified_content = content.upper()

        # Write the modified content to the output file
        with open(output_filename, 'w') as outfile:
            outfile.write(modified_content)

        print(f"The file has been successfully modified and saved as {output_filename}")

    except FileNotFoundError:
        print(f"Error: The file {input_filename} was not found.")
    except Exception as e:
        print(f"An error occurred: {e}")

# Example usage
input_filename = 'example.txt'
output_filename = 'modified_example.txt'
modify_file(input_filename, output_filename)
```

### **Error Handling Lab 🧪:**
This program prompts the user to enter a filename, handles errors if the file doesn't exist, and deals with any other reading issues.

```python
def read_file_with_error_handling():
    filename = input("Enter the filename to read: ")

    try:
        # Attempt to open the file
        with open(filename, 'r') as file:
            content = file.read()
            print("File content:")
            print(content)

    except FileNotFoundError:
        print(f"Error: The file {filename} was not found.")
    except IOError:
        print(f"Error: Could not read the file {filename}.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

# Example usage
read_file_with_error_handling()
```

### How they work:
1. **File Read & Write Challenge 🖋️**:
   - The `modify_file()` function reads the content of the specified input file, converts it to uppercase, and writes it to a new file.
   - Error handling ensures that the program informs the user if the input file doesn't exist or if there's any other issue.

2. **Error Handling Lab 🧪**:
   - The `read_file_with_error_handling()` function prompts the user for a filename.
   - It includes error handling to deal with cases where the file doesn't exist (`FileNotFoundError`), there’s an issue with reading the file (`IOError`), or any other unforeseen errors.

Let me know if you'd like further modifications or explanations!
