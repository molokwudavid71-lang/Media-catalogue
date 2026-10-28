# Media-catalogue

A Python project that models a media catalogue using object-oriented programming. It stores movies and TV series, validates their data, and prints a formatted catalogue.

## Features

- **`Movie` class** with title, year, director, and duration
  - Validates input: the title and director can't be empty, the year must be 1895 or later, and the duration must be positive
- **`TVSeries` class** that inherits from `Movie`
  - Adds `seasons` and `total_episodes`, which must both be 1 or greater
  - Overrides `__str__` to show seasons and episodes
- **`MediaCatalogue` class** that stores media items
  - `add()` accepts only `Movie` or `TVSeries` objects
  - `get_movies()` and `get_tv_series()` filter the catalogue by type
  - `__str__()` prints a numbered list grouped into Movies and TV Series
- **Custom error handling** with `ValueError` for invalid data and a custom `MediaError` for items that can't be added

## Concepts Practised

- Classes and instantiation
- Inheritance and `super()`
- Method overriding (`__str__`)
- `isinstance()` and `type()` checks
- Custom exceptions
- `try` / `except` error handling
- List comprehensions and f-strings

## Usage

1. Save the code as `build media catalogue.py`.
2. Run it from your terminal:

   ```bash
   python "build media catalogue.py"
   ```

3. The script creates a `MediaCatalogue`, adds two movies and two TV series, then prints the catalogue grouped into **Movies** and **TV Series**.

To add your own items, create a `Movie` or `TVSeries` and pass it to `catalogue.add()`:

```python
catalogue = MediaCatalogue()

# Movie(title, year, director, duration_in_minutes)
catalogue.add(Movie('Inception', 2010, 'Christopher Nolan', 148))

# TVSeries(title, year, director, episode_duration, seasons, total_episodes)
catalogue.add(TVSeries('Breaking Bad', 2008, 'Vince Gilligan', 47, 5, 62))

print(catalogue)
```

Invalid data (for example an empty title or zero seasons) raises a `ValueError`. Adding anything that isn't a `Movie` or `TVSeries` raises a `MediaError`. The script catches both and prints a clear message.

## Requirements

- Python 3.x
- No external libraries

## Acknowledgements

This project was built as part of the [freeCodeCamp](https://www.freecodecamp.org/) Python certification.  The project brief comes from freeCodeCamp's curriculum, and the solution was written by me while working through the course.

