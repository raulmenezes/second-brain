---
tags:
  - area/devops
  - area/knowledge
  - topic/javascript
  - topic/project
  - topic/testing
---

# Hands On UI Interview

**npx create-react-app my-app --template typescript**  **https://studio.webcomponents.dev/**

**https://playcode.io/react**

"axios": "0.10.0"
 **Had issues with her local code editor Issues with Usercard not passing props** 
**react-router-dom**

**Make sure people use Typescript**

Task 1: Component Creation
**Objective:** Assess the candidate's ability to create React components and manage state.

- **Task 1 Description:**
	- Create a React functional component named **UserCard**.
	- The component should take username, email, phone and website as props.
	- Display the user's profile information, including the username, email, phone and website.
	- Implement local state within the component to manage whether to show or hide the user's phone.
- **Evaluation Criteria:**
	- Correct implementation of the **UserCard** component.
	- Proper usage of props and state.
	- Ability to conditionally render elements based on the state.

Task 2: API Integration
**Objective:** Evaluate the candidate's skills in making API requests and handling asynchronous operations.

- **Task 2 Description:**
	- Implement a new component, **UserList**, that displays a list of users (**UserCard**) 
	- Use the fetch API or any library of your choice to make a GET request to a mock API endpoint (e.g. https://jsonplaceholder.typicode.com/users).
	- Fetch user details from the API and display the list of users’ username, email, phone and website
	- Level 2 - Fetch another API endpoint and combine the responses together e.g. https://jsonplaceholder.typicode.com/photos 
- **Evaluation Criteria:**
	- Proper handling of asynchronous operations.
	- Correct usage of lifecycle methods (if applicable).
	- Ability to parse and display data from the API.

Task 3: Routing
**Objective:** Evaluate the candidate's knowledge of React Router for navigation.

- **Task Description:**
	- Create with two pages: Home and Users.
	- Use React Router to navigate between these pages.
	- Display a navigation bar that allows users to switch between Home and About.
- **Evaluation Criteria:**
	- Proper usage of React Router.
	- Implementation of navigation between different pages.
	- Clear and organized project structure.

Task 4: Performance Optimization and Form Enhancement
**Objective:** Optimize performance of UserList component
- **Task 3 Description:**
	- Apply performance optimization techniques, such as memoization, to the UserList component to prevent unnecessary renders.
- **Evaluation Criteria:**
	- Successful implementation of performance optimization in the UserList component.

Check understanding with web components

Task 5 Optional: State Management
**Objective:** Assess the candidate's understanding of state management in React.

- **Task Description:**
	- Extend the multi-step form from Task 2 in the first interview to allow editing of user details fetched from the API. Use Redux for form state management.
	- Create a simple counter application using React.
	- Implement two buttons: one to increment the counter and another to decrement it.
	- Display the current count on the screen.
- **Evaluation Criteria:**
	- Proper state management.
	- Handling of user interactions (button clicks) to update the state.
	- Clear understanding of React state concepts.

react-redux for state management and react-router-dom for routing.

## Related
- [[simple-work-flow-service-swf]]
- [[sns-simple-notification-service]]
