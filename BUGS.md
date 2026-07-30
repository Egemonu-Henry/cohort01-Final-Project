1. Bug: [a blank page shows up when I run "npm run dev" ]
    - what is broken : from my console an error "App.jsx:10 Uncaught ReferenceError: useState is not defined"

    - where the Bug is: App.jsx: 10
    - why is it broken: useState wasn't imported from react
    - how I fixed it : I fixed it by importing useState from react. ie import {useState} from "React"