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