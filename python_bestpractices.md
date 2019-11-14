# Some Python best practices and Python Enhancement Proposal (PEP)

* Zen of Python

    ```python
    import this
    ```

* Print
  * Template: this gives flexibility in passing parameters to the print function and prevents direct access to string 'format' method which may cause security risks.

    ```python
        from string import Template

        scores = (90, 65, 70, 80)
        grades = ("A", "D", "C", "B")
        combined = zip(scores, grades)

        for item in combined:
            tmpl = Template("score: ${score} grade: ${grade}")
            final = tmpl.substitute(score=item[0], grade=item[1])
            print(final)
    ```

  * Using template with a dictionary data structure

    ```python
        from string import Template

        info = {
            "description": "This is a fun game.",
            "game": "cricket"
            }

        tmpl = Template("description: ${description} \ngame: ${game}")
        output = tmpl.substitute(info)
        print(output)
    ```

  * string format

    ```python
       day_of_the_week = "Saturday"
       game = "Football"
       print(f"{day_of_the_week} is always an exciting day for me.")

       print("{0} is always enjoyable watching {1}".format(day_of_the_week, game))      
    ```

* functools.lru_cache() decorator
  can be used to perform memoization in dynamic programming
  
  ```Python
    import functools

    @functools.lru_cache()
    def fib(nth):
        if nth == 1 or n == 2:
            # base case
            return 1
        else:
            # recursion
            return fib(nth - 1) + fib(nth + 1)
  ```
