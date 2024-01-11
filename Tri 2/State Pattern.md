# State Patterns

* Notes for 1/11/2024 quiz on State Pattern
* State is the current condition of object or component in code
* Problematic if you represent state with booleans and if else statements cause you have a lot of variables and complexity
* Enums (string mask for numerical store) you can use to represent state
* You build FSM to keep track of state and logic to handle transitions from one state to another
  * Assumes finite states and object can only be in one state at a time

## FSM Rules

* FSM is a graph of nodes and edges where nodes are states and edges are one way transitions between states,
* Only one state at a time, and you can only move to another state by following the transitions to the other state from the existing state you are at

## FSM Implementation Example

```cpp
enum State {
    CONNECTING,
    CONNECTED,
    ON_HOLD
};

int main() {
    State s = CONNECTING;
    // all transitions from connecting state to other states handled here
    // each state that has edges/transitions has a block like this  
    if (s == CONNECTING) {

    }
    else if (s == CONNECTED) {

    }
    else if (s == ON_HOLD) {
        
    }
}
```
