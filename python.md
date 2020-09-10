
# Python

Truquillos y demases aprendidos del programa especializado "Python for Everybody" y la certificación "Google Automation with Python", ambos de Coursera:

[Python for Everybody](https://www.coursera.org/learn/python)

[Google IT Automation with Python](https://www.coursera.org/professional-certificates/google-it-automation)

## Useful idiomatics

### Shortest simple histogram

### "json" Library

`json.dumps(js, sort_keys=True, indent=4)` beautifies your js prints 10/10



### One line text file search

En este caso, la linea suma todos los valores numericos que se encuentren en `tekets.txt`

```
import re

print( sum( [ int(i) for i in re.findall( '[0-9]+' , open('tekets.txt').read() ) ] ) )
```

### .format() Cheat Sheet

[Cheat Sheet](format.png)

## Script-azos

### El clásico buscador de factores primos

```
def print_prime_factors(number):
  # Start with two, which is the first prime
  factor = 2
  # Keep going until the factor is larger than the number
  while factor <= number:
    # Check if factor is a divisor of number
    if number % factor == 0:
      # If it is, print it and divide the original number
      print(factor)
      number = number / factor
    else:
      # If it's not, increment the factor by one
      factor += 1
  return "Done"
```

### Reemplazo de la ultima palabra de una oración por una nueva.

```
def replace_ending(sentence, old, new):
	# Check if the old string is at the end of the sentence 
	if sentence.endswith(old):
		# Using i as the slicing index, combine the part
		# of the sentence up to the matched string at the 
		# end with the new string
		i = sentence.index(old)
		tmp = sentence[i+len(old):]
		while old in tmp:
			i = i + tmp.index(old) + len(old)
			tmp = sentence[i+len(old):]
		new_sentence = sentence[:i] + new
		return new_sentence

	# Return the original sentence if there is no match 
	return sentence
	
print(replace_ending("It's raining cats and cats", "cats", "dogs")) 
# Should display "It's rainikang cats and dogs"

```reclamalo

