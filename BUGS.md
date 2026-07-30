1. Bug: [a blank page shows up when I run "npm run dev" ]
    - what is broken : from my console an error "App.jsx:10 Uncaught ReferenceError: useState is not defined"

    - where the Bug is: App.jsx: 10
    - why is it broken: useState wasn't imported from react
    - how I fixed it : I fixed it by importing useState from react. ie import {useState} from    "React"

2. Bug: [search does not work]
    - what is broken: Typing into the search bar does not trigger a movie search.
    - Where the bug is: App.jsx (useEffect responsible for searching) and no TMBD API key
    - Why is it broken: The useEffect dependency array is empty ([]), so it only runs once when the component mounts.
    - How I fixed it: Added query to the dependency array and included a cleanup function to clear the timeout and added an API key.

3. Bug 3: Watchlist is not saved after refreshing
    - What is broken: Movies added to the watchlist disappear after refreshing the page.
    - Where the bug is: App.jsx (App.jsx: 40 "Save watchlist to localStorage whenever it changes")
    - Why is it broken: Different keys were used for saving and retrieving the watchlist (movieWatchList & myWatchList).
    - How I fixed it: Used the same Local Storage key for both saving and loading (movieWatchList).

4. Bug 4: Watchlist filters display the wrong movies
    - What is broken: Selecting "Watched" displays unwatched movies, and vice versa.
    - Where the bug is: App.jsx (Filter logic)
    - Why is it broken: The filter conditions for watched and unwatched movies were reversed.
    - How I fixed it: Corrected the filter conditions.

5.  Bug 5: Duplicate movies can be added to the watchlist
    - What is broken: The same movie can be added multiple times.
    - Where the bug is: App.jsx (addToWatchlist function)
    - Why is it broken: There was no check to determine if the movie already existed in the watchlist.
    - How I fixed it: Introduce a condition to Checked whether the movie already exists before adding it.

6. Bug 6: Multiple API requests are made while typing
    - What is broken: Several search requests are sent when typing quickly.
    - Where the bug is: App.jsx (useEffect debounce)
    - Why is it broken: The timeout created by setTimeout() was never cleared.
    - How I fixed it: Added a cleanup function to cancel the previous timeout before creating a new one.

7. Bug 7: Error message remains after a successful search
    - What is broken: An old error message continues to display even after a successful search.
    - Where the bug is: fetchMovies() function in App.jsx
    - Why is it broken: The error state was never reset before making a new API request.
    - How I fixed it: Cleared the error state before fetching new data ["setError(null)"];.
