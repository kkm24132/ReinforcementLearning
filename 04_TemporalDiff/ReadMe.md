
### Temporal Difference Learning

- Temporal Difference is part of Prof Sutton's PhD work in 1984
- Lookup table case
- Proof : Van Roy and J.Tsitsikhs, 1997 - IEEE Trs on Autonomous Contribution
- Simplest TD Method: V(S_t) <- V(S_t) + alpha * {R_t+1 + Gamma . V(S_t+1) - V(S_t)}
- In TD method, we keep on updating the values of states as they are visited.
- TD Algorithms perform Bootstrapping - i.e. update values of states based on values of other states
