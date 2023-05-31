# Quantum-Coin-Toss
This code allows you to play a simple game of coin toss with a quantum twist, where you try to guess the state of a quantum coin (Heads or Tails) based on a measurement outcome.

1. The code begins by importing the random module, which is used to generate a random state for the quantum coin.

2. The coin_toss function is defined, which represents a single round of the coin toss game.

3. Inside the coin_toss function, a random state ('H' for Heads or 'T' for Tails) is generated for the quantum coin using random.choice(['H', 'T']). This simulates flipping the coin.

4. A QuantumCircuit is created with one qubit and one classical bit using QuantumCircuit(1, 1).

5. If the coin state is 'H' (Heads), the Hadamard gate h(0) is applied to the qubit. This puts the qubit in a superposition of |0⟩ and |1⟩, representing an equal chance for the outcome to be Heads or Tails.

6. The qubit is then measured using circuit.measure(0, 0), which performs a measurement of the qubit and stores the result in the classical bit.

7. The Qiskit simulator is used to execute the circuit on a local quantum simulator. Aer.get_backend('qasm_simulator') retrieves the simulator backend.

8. The measurement outcome is obtained from the simulation result using result.get_counts(circuit).most_frequent(). The result is converted from a binary string to an integer using int(..., 2).

9. The measurement is mapped to either 'H' or 'T' based on the outcome. If the measurement is 0, it corresponds to 'H', and if it is 1, it corresponds to 'T'.

10. The guessed state is compared to the actual coin state. If they match, a success message is printed. Otherwise, a failure message is printed along with the actual coin state.

11. Finally, the coin_toss function is called to play a round of the game.
