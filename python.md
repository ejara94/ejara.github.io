
# Python

Truquillos y demases aprendidos del programa especializado "Python for Everybody" y la certificación "Google Automation with Python", ambos de Coursera:

[Python for Everybody](https://www.coursera.org/learn/python)

[Google IT Automation with Python](https://www.coursera.org/professional-certificates/google-it-automation)

## Useful idiomatics

### Shortest simple histogram

### "json" Library

### One line text file search

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
      factor += 1
      # If it's not, increment the factor by one
      factor += 1
  return "Done"
```

