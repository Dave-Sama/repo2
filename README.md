import re

def extract_text(text):
  """
  Extracts the text between "========" and ">>>>>>>".
  """
  match = re.search(r"(?<========)(.*)(>>>>>>>)", text, flags=re.DOTALL)
  # Corrected line
  if match:
    return match.group(1)
  else:
    return None

# Example usage (unchanged)
with open("test1.txt", "r") as file:
  text = file.read()

extracted_text = extract_text(text)

if extracted_text:
  print(extracted_text)
else:
  print("No text found between markers")
