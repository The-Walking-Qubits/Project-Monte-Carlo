Project Name : Quantum Walks and Monte Carlo

Team Name : The Walking Qubits

Members:
1. Name:Ashna Yadav
   WISER Enrollment Id:gst-G2T7G514NBhDM97

Summary:
Task 1 - Familiarising with the concept
We started the project by reading the paper and supplementary material focusing on:
Quantum Walks - a quantum equivalent to classical random walks, whereby the direction of the walker is based on quantum superposition and interference.
Monte Carlo method - a type of algorithm that relies on repeated random sampling, government by probability and statistics
Why Quantum? - There are classical simulations that are readily available, however, when using quantum implementations we can exploit parallelism and interference that can allow the generation to happen quicker and more complex distributions can be generated either, which can be difficult to do with classical simulations.

We noted everything down into a report which covered 2 pages.

Task 2 - Moderately generalising Gaussian Distribution from n Levels
We first implemented the basic 2-level QGB.
What happens:
A "coin" type qubit, determines the movement of the walker (left or right).
We apply a Hadamard gate, to achieve equal superposition, so we can view it as a flip of a fair coin. 
Controlled shift operations advance the "walker" register based on the state of the coin's qubit.
When we have had enough time steps, interference patterns come into existence which will generate the probability distribution.
2-level to n levels:
Starting with the completion of simple 2-level coding, we had already captured the repetitive pattern of coin toss + shift. 
This was converted into a function, since the number of levels is now a variable.
The function still designs the circuit layout as appropriate for any n, by applying the same logic for n to develop the circuit.
Output:
By running the circuit with appropriate shots will generate a histogram that will closely match the Gaussian curve.

Task 3 – Generating Other Distributions
We aimed to modify the Gaussian QGB to create other distributions. 
1. Exponential Distribution:
Plan:
Start with a biased variation of the QGB to create a 2-level discrete distribution (this means we are replacing the Hadamard with an RX(theta) rotated coin , to create a biased coin flip).
Add a reset gate after every peg/stage so that you can reinitialize the qubits to control interference.
Add the final correcting CNOT gate to fix any correlations we don't want.

The key challenge, in the case of an exponential, is finding the right values for theta (rotation angle) and lambda (decay rate) to fit a good exponential distribution. 
We plug values for theta and lambda in, and repeat the previous versions in order until you see the output histogram look more like the target distribution.

2. Quantum Walk Distribution: 
Concept:
Instead of biasing the coin, you can manipulate the phases and interference patterns of the walker, so that the final histogram looks more like a quantum walk (specifically, higher probabilities at the edges, consistent with constructive interference).
This involves carefully manipulating the rotation gates and phase shifts in order to remove the perfectally symmetrical Gaussian shape.

Issues faced:
Parameter Finding: Finding just the correct theta and lambda was not easy, as small changes lead to large differences in the output. 
Visualizing circuits: While we have an n-level circuit that can be expanded, a circuit for n>2 becomes complicated quickly.
That also made it difficult to check what the circuit was doing given that the mapping of a 2-level to an n-level circuit was not skeletally obvious when debugging from the Circuit Drawer in Qiskit. 
Accuracy of the distributions: While some runs yielded too noisy shapes or distortions, hence the need to get the parameters right, and maximize the shots to improve statistics.

Outcomes:
Successfully had a scalable n-level gaussian QGB.
Modified it enough to create an exponential and quantum walk type distribution.
Awareness of trade-offs associated to gates, biasing actions, and reseting states for shaping probability distributions.

This project shows how quantum circuits have the potential to shape outputs to produce many types of statistical patterns, and extend toward quantum simulations, probabilistic models, variational algorithms, deep learning and machine learning.

   

Project Presentation deck
