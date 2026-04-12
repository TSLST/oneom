---
Type: Course
Use: Notes and synthesis over the course of Quantum Computing Learning. The file will contain code, notes, excerpts, definitions, links, ressources that help grasp the usage of Quantum Computers.
Tags:
Creation: 2026-02-28
Update: 2026-02-28
Contributors: 神縁
Links:
- [[quantum]]
- [[qiskit]]
- [[jupyternotebook]]
---

# Quantum Computing

**Quantum Computing as a side quest for intellectual self-realisation**

---

## North Star

AMI-type research ou quantum algorithmics R&D<br>
Horizon réaliste: 18-24 mois pour être contributeur crédible<br>
Horizon ambitieux: publication ou contribution open-source en 12 mois<br>

---

## Mindset

> Einstein wrote in 1952 that quantum mechanics appears to him to be:<br>
> “a system of delusion of an exceedingly intelligent paranoiac concocted of incoherent elements of thought“
> ***


<br>

* Complex numbers
* Matrix/scalar fluency
* Physically fit — asset for cognitive endurance
* Financial constraints: zero-cost path required

---

## Fields of Application

here are some potential applications of quantum computing:
1. **Chemistry and Materials Science**:<br>
Simulating molecular interactions and predicting new materials with desired properties can help in drug discovery, battery development, and material engineering.
2. **High Energy Physics**:<br>
Quantum computers may help in modeling and simulating particle collisions to better understand the fundamental forces of nature and potentially discover new subatomic particles.
3. **Logistics and Optimization**:<br>
Quantum algorithms have the potential to solve complex logistical problems, such as finding the shortest path or most efficient routes for delivery trucks, more efficiently than classical computers.
4. **Cryptography**:<br>
While quantum computing can break some of today's encryption methods (such as RSA), it can also help develop new unbreakable encryption techniques and provide improved security protocols for online transactions and communication.
5. **Finance**:<br>
Quantum computers could potentially be used to analyze market trends, make investment decisions, and perform risk analyses, providing valuable insights to investors and financial institutions.
6. **Artificial Intelligence**:<br>
Quantum machines may enable new AI techniques that can outperform classical computers in tasks such as pattern recognition, natural language processing, and machine learning.
7. **Simulating complex systems**:<br>
Quantum simulation could be used to understand and manipulate phenomena in fields such as climate science, meteorology, and condensed matter physics.
8. **Drug Discovery and Medicine**:<br>
Quantum computers can help design new pharmaceuticals by simulating interactions between molecules and potential drugs, thus expediting the drug discovery process.
9. **Earth Sciences**:<br>
Applications include predicting earthquakes, simulating climate change, and modeling complex geological formations.

---

## Notes

---
### QC — Quantum Computing

> Noisy intermediate-scale quantum (NISQ)
> ***
> Noisy intermediate-scale quantum computers is a term coined by John Preskill of CalTech. This refers to systems that do not yet have full error-correction (thus noisy) and have dozens to thousands of qubits – well short of the 10^6C (qubits) necessary for scaled fault-tolerant computing.
> ***

___
#### I.1 Superposition, Entanglement and Reversibility

> 1.1 Quantum Computer Definition
> ***
> A quantum computer is a device that leverages specific properties described by quantum mechanics to perform computation
> ***

> 1.2 The Superposition Principle
> ***
> The linear combination of two or more state vectors is another state vector
in the same Hilbert space and describes another state of the system.
> ***

A Hilbert space is the mathematical arena in which quantum states live. It is a vector space equipped with an inner product — the bra-ket $ \langle\phi|\psi\rangle $ — that allows you to measure angles and distances between states, just as the unit circle did for 2D rotations. Crucially it is **complete**, meaning there are no "gaps" in the space, so infinite superpositions of states converge to valid states within it. Each quantum state is a unit vector in this space, orthogonal states are perfectly distinguishable outcomes, and the normalization condition $ \sum|a_i|^2 = 1 $ is simply the requirement that the vector sits on the unit hypersphere of the Hilbert space.

<br>

Why $ |\psi\rangle = \frac{1}{\sqrt{2}}|0\rangle + \frac{1}{\sqrt{2}}|1\rangle $
rather than:
$ |\psi\rangle = \frac{1}{2}|0\rangle + \frac{1}{2}|1\rangle $ ?

The reason comes directly from the connection to the unit circle and orthogonal matrices. The coefficients in a quantum superposition are called **amplitudes**, and the rule is:
> The **square** of each amplitude must give the probability of measuring that state — and all probabilities must sum to 1.

So for equal superposition you need two numbers `a` and `b` such that:

$$a^2 + b^2 = 1 \quad \text{(the normalization condition)}$$

- With `1/√2`: $\left(\frac{1}{\sqrt{2}}\right)^2 + \left(\frac{1}{\sqrt{2}}\right)^2 = \frac{1}{2} + \frac{1}{2} = 1$ ✓
- With `1/2`: $\left(\frac{1}{2}\right)^2 + \left(\frac{1}{2}\right)^2 = \frac{1}{4} + \frac{1}{4} = \frac{1}{2}$ ✗

The second version only accounts for half the total probability — the state vector doesn't live on the unit circle, it falls short of it.

This is exactly the same constraint as orthogonal matrices:<br>
the amplitudes `a` and `b` are the cosine and sine of some angle θ on the unit circle, satisfying `cos²θ + sin²θ = 1`.<br>
For equal superposition that angle is 45°, giving `cos 45° = sin 45° = 1/√2` — the same value you just saw in the 45° orthogonal matrix.

> 1.3 The Born rule
> ***
> In a superposition of states, the modulus squared of the amplitude of a state
is the probability of that state resulting after measurement. Furthermore,
the sum of the squares of the amplitudes of all possible states in the
superposition is equal to 1. So, for the state $ |\psi\rangle = \alpha|0\rangle + \beta|1\rangle $, we have:
> $$ |\alpha|^2 + |\beta|^2 = 1 $$
> ***

> 1.4 Entanglement
> ***
> Two systems are in a special case of quantum mechanical superposition
called entanglement if the measurement of one system is correlated with
the state of the other system in a way that is stronger than correlations
in the classical world. In other words, the states of the two systems are
not separable. We will explore the precise mathematical definitions of
separability and entanglement later in this book.
> ***

> 1.5 Reversibility of Quantum Computation
> ***
> All operators used in quantum computation other than for measurement
must be reversible
> ***

___
#### I.2 Quantum Information Sciences — QIS
- Computation
- Communication
- Sensing

    There is an emerging class of sensors for detecting position, navigation and timing (PNT) at the atomic scale. These micro-PNT devices can provide highly accurate positioning data when GPS is jammed or unavailable.

##### Quantum-specific protocols

Quantum Teleportation
Superdense Coding

___
#### II A Brief History of Quantum Computing

> In computer science and quantum computing, it is often important to
evaluate how efficient an algorithm is.
> ___
> * big-$ O $: The **UPPER** bound of the worst case of running an algorithm<br>
> * big-$ \Omega $: The **LOWER** bound of the worst case scenario<br>
> 
> **E.G.**: while Deutsch’s problem takes at worst $ O(n) $ steps to solve on a classical computer, Deutsch-Jozsa’s algorithm solves the problem in one step on a quantum compute
> ___
<br>

+ Richard Feynman
+ Paul Benioff
+ Yuri Manin
+ David Deutsch (physicist at Oxford) + Richard Jozsa
+ Umesh Vazirani and his student Ethan Bernstein (BV algorithm)
+ Daniel Simon Montreal 1994
+ Seth Lloyd, working at Los Alamos (building a working quantum computer)
+ Peter Shor 1994 Bell Labs (algorithm for factoring large numbers into two prime factors)

> Shor studied the work of Deutsch, BV and Simon and realized he could construct an algorithm for factoring large numbers into two prime factors; factoring large numbers is believed to be intractable on a classical computer, but Shor’s factoring algorithm runs quickly on a QC.<br>
> Factoring large numbers is, of course, the intentionally hard problem at the core of public key cryptography (PKC) as implemented in the RSA algorithm, the kind of cryptography that is the basis of almost all communications today over the internet. This includes securely sending credit card numbers, bank payments and ensuring the security of online messaging systems.

**QFT**: Quantum Fourier Transform (Described by BV)

+ Lov Grover contributed to the quantum algorithm arsenal by demonstrating that one can achieve Quadratic speedup in a search algorithm on a QC.

**Quadratic speedup**: if an algorithm would take $ O(n) $ steps on a classical computer, we can achieve the same goal in $ O(\sqrt{n}) $ steps on a QC.

+ Farhi and Gutmann (continuous time Hamiltonian version of Grover’s algorithm)
+ David DiVincenzo (Quantum Computation key criteriqs)

___
##### Quantum Computation key criterias

1. A scalable physical system with **qubits that are distinct** from one another and the ability to **count** exactly how many qubits there are in the system (no fudging allowed). The system can be accurately represented by a **Hilbert space**.
2. The ability to **initialize** the state of any qubit to a definite state in the computational basis. For example, setting all qubits to state $ |0\rangle $ if the computational basis vectors are $ |0\rangle $ and $ |1\rangle $.
3. The system’s qubits must be able to **hold** their state. This means that the system must be **isolated** from the outside world, otherwise the qubits will decohere. Some decay of state is allowed ($ \epsilon $, where $ \epsilon $ is a small quantity). In practice, the system’s qubits must hold their state **long enough to apply the next operator** with assurance that the qubits have not changed state due to outside influences between operations.
4. The system must be able to **apply a sequence of unitary operators** to the qubit states. The system must also be able to apply a unitary operator to two qubits at once. This entails entanglement between those qubits. As DiVincenzo states in his paper, “...entanglement between different parts of the quantum computer is good; entanglement between the quantum computer and its environment is bad, since it corresponds to decoherence”.
5. The system is capable of making “strong” **measurements** of each qubit. By strong measurement, DiVincenzo means that the measurement says “which orthogonal eigenstate of some particular Hermitian operator the quantum state belongs to, while at the same time projecting the wavefunction of the system irreversibly into the corresponding eigenfunction.” This means that the **measuring technique** in the system actually does measure the state of the qubit for the property being measured and **leaves the qubit in that state**. DiVincenzo wants to prevent systems that have weak measurement, in other words, measuring techniques that do not couple with the qubit sufficiently to render it (*Fix it*) in that newly measured state. At the time he wrote the paper, many systems did not have sufficient coupling to guarantee projection into the new state

___
##### QC Building

+ Yasunobu Nakamura **built** and demonstrated a functioning, controllable
superconducting qubit
+ Cirac and Zoller proposed an ion trap as the physical system to perform quantum computation. In this setup, lasers are used to ionize atoms which are then trapped in electric potentials. 

---

## Plan

1. [*] We recommend first assigning chapters 1 and 2 as pre-reading (17/379) 
1. [ ] Next, we suggest covering the chapters on unitary operators, measurement and quantum circuits with exercises on the Github site to check knowledge.
1. [ ] We then recommend spending the bulk of the course in Part II to provide the students with hands-on experience with the code

---
### Month 1 — Objectives

- [ ] Shor's algorithm — comprendre la structure<br>
    (factorisation = cryptographie = blockchain = pont possible)<br>
- [ ] Premier notebook publié sur GitHub<br>

___
#### Week 1 — Foundations (2026-03-23)

- [*] Installer Qiskit + Jupyter sur Node 2<br>
    pip install notebook qiskit qiskit-aer<br>
    jupyter notebook<br>
- [ ] Implémenter le circuit de Bell<br>
    — 5 lignes, fondement de l'intrication quantique<br>
    — Comprendre chaque ligne, pas juste exécuter<br>
- [*] Lire Hidary chapitres 1-2 (bases maths + postulats QM)<br>
- [ ] Regarder "Quantum Computing for Computer Scientists"<br>
    (Microsoft Research, YouTube)<br>
- [ ] Relancer Node 1<br>
- [ ] Installer environnement complet de dev Node 1<br>

___
##### Venv

___
###### BashRC Aliases

```bashrc
export OPT="/home/opt" #//Classique
export QENV="$OPT/projects/oneom/qenv"
alias oneom='source $QENV/bin/activate && jupyter notebook'
```

___
###### Venv

```bash
# 1. Installer python3-full si pas déjà là
sudo apt install python3-full python3-venv

# 2. Créer un venv dédié quantum (où tu veux, ex: home)
python3 -m venv $QENV

# 3. Activer le venv
source $QENV/bin/activate
    #//Ton prompt change: (quantum-env) user@machine

# 4. Installer dans le venv — plus d'erreur
pip install notebook qiskit qiskit-aer

# 5. Lancer Jupyter
jupyter notebook
```

___
###### Activation

Pour que VSCodium utilise ce venv comme kernel Jupyter:<br>
Ctrl+Shift+P → "Python: Select Interpreter" → choisir `$QENV/bin/python`
<br><br>
À chaque nouvelle session terminal, il faudra réactiver avec `oneom`.

___
###### Jupyter Setup

```bash
# Verifier que tout fonctionne
python3 -c "import qiskit; print(qiskit.__version__)"
    #//=> 2.3.1

# Enregistre le kernel Jupyter avec le bon nom
python3 -m ipykernel install --user --name=qenv --display-name "OneOM"

# Lance Jupyter
jupyter notebook --notebook-dir=$OPT/projects/oneom
    #//=> Ça ouvre le navigateur sur `localhost:8888`
```

```bash
# Pour ne plus avoir à le taper à chaque fois:
jupyter notebook --generate-config
```
Puis édite le fichier généré `~/.jupyter/jupyter_notebook_config.py`, cherche la ligne:
```python
# c.ServerApp.root_dir = ''
```
Remplace-la par:
```python
c.ServerApp.root_dir = '/home/opt/projects/oneom'
```

Ensuite un simple `jupyter notebook` pointera toujours sur le bon dossier.

___
###### Folders

Crée aussi la structure de dossiers pour garder le travail organisé:
```bash
mkdir -p /home/opt/projects/oneom/prod/{circuits,algorithms,notes}
```
```
oneom/
└── prod/
    ├── circuits/     ← Bell, Deutsch, Grover...
    ├── algorithms/   ← implémentations complètes
    └── notes/        ← notebooks d'exploration
```

___
###### Circuit de Bell

1. Bell State<br>
A Bell state in quantum computing is a special type of entangled state where two qubits are linked such that the state of one qubit instantly influences the state of the other, no matter the distance between them.
2. Superposition<br>
The principle that a qubit can exist in multiple states (0 and 1) simultaneously, rather than being in a single state like a classical bit.
3. Hadamard Gate<br>
A basic operation that transforms a qubit into an equal superposition of its 0 and 1 states, creating a state where the qubit has a 50% chance of being measured as 0 and a 50% chance of being measured as 1.
4. The CNOT (Controlled NOT)<br>
GateA two-qubit operation where the state of the second qubit (target) is flipped if the first qubit (control) is in the state 1, otherwise, the target qubit remains unchanged.
5. Pauli Operators<br>
A set of three basic matrices (Pauli-X, Pauli-Y, and Pauli-Z) used to describe quantum gates that can change the state of a qubit by flipping its state, rotating it, or inverting its phase.

        In quantum computing, operators like ZZ, XX, and YY perform specific transformations on qubit states, altering their properties such as phase, amplitude, or entanglement.

___
###### Pauli Operators/Matrices

Four matrices $ I, X, Y, Z $
They are Quantum Gates

▶️ The Pauli-X Gate $(x)$

Bit-Flip gate, a classical NOT as gate in Quantum<br>
$ 
    X = 
    \begin{pmatrix} 
        0   & 1 \\ 
        1   & 0 
    \end{pmatrix} 
$

**Action:** It maps $ |0\rangle \rightarrow |1\rangle $ and $ |1\rangle \rightarrow |0\rangle $, a 180° or $\pi$ radians rotation around the X axis of the Bloch sphere

▶️ The Pauli-Z Gate $(z)$

Phase-Flip gate, no classical equivalent<br>
$ 
    Z = 
    \begin{pmatrix} 
        1   & 0 \\ 
        0   & -1 
    \end{pmatrix} 
$

**Action:** It leaves $|0\rangle$ unchanged but maps $ |1\rangle \rightarrow -|1\rangle $, a 180° or $\pi$ radians rotation around the Z axis of the Bloch sphere

▶️ The Pauli-Y Gate $ (y) $

Bit-Flip AND Phase-Flip gate with a complex unit (imaginery $ i $)<br>
$ 
    Y = 
    \begin{pmatrix} 
        0   & -i \\ 
        i   & 0 
    \end{pmatrix} 
$

**Action:** It maps $ |0\rangle \rightarrow i|1\rangle $ and $ |1\rangle \rightarrow -i|0\rangle $, a 180° or $\pi$ radians rotation around the Y axis of the Bloch sphere

▶️ The Pauli-Bonus Gate $(I)$

Identity Matrix<br>
$ 
    I = 
    \begin{pmatrix} 
        1   & 0 \\ 
        0   & 1 
    \end{pmatrix} 
$

**Action:** It does not transform the vectors of the Bloch sphere

<a href="https://www.youtube.com/watch?v=93-zLTppFZw&list=PLOFEBzvs-Vvo4oV-fMl1EAuZmJhI5qA_i&index=3" class="hover-effect" data-title="[Qiskit YouTube playlist](https://www.youtube.com/watch?v=93-zLTppFZw)">
    <img src="https://images.icon-icons.com/17/PNG/256/social_youtube_2234.png" alt="Quantum Computing for Computer Scientists" width="32">
</a> 👉 Qiskit YouTube playlist (1/7)<br><br>

Crée un nouveau notebook, sélectionne le kernel OneOM (Preferred Kernel as well), et colle ce code:
```bash
from qiskit import QuantumCircuit
from qiskit_aer import AerSimulator

# Circuit: 2 qubits, 2 bits classiques
qc = QuantumCircuit(2, 2)

# Hadamard sur qubit 0 — crée la superposition
qc.h(0)

# CNOT — intrication des deux qubits
qc.cx(0, 1)

# Mesure
qc.measure([0, 1], [0, 1])

# Simulation
sim = AerSimulator()
job = sim.run(qc, shots=1024)
result = job.result()
counts = result.get_counts()

print("Résultats:", counts)
qc.draw('text')
    #//=> Résultat attendu: uniquement {'00': ~512, '11': ~512} — jamais 01 ou 10. C'est l'intrication: les deux qubits sont corrélés, mesurer l'un détermine l'autre instantanément. C'est le fondement de tout le reste.
```

Le circuit de Bell va dans `circuits/w1_bell.ipynb`.<br>
Lance et dis-moi ce que tu obtiens.<br><br>
Pour VSCodium: Ctrl+Shift+P → Python: Select Interpreter → naviguer vers /home/opt/projects/oneom/qenv/bin/python.

___
#### Week 2 — First algorithms

- [ ] Algorithme de Deutsch-Jozsa<br>
    — Premier algorithme quantique qui bat classique<br>
    — Intuition: parallélisme quantique via superposition<br>
- [ ] Algorithme de Grover (comprendre, pas encore coder)<br>
    — Recherche en O(√N) vs O(N) classique<br>
    — Ton terrain: données, recherche, optimisation<br>

___
#### Week 3 — 

___
#### Week 4 — 

___
#### Week 5 — 

---
### Month 2 — 

---

## Resources

---
### Books

* "Quantum Computing: An Applied Approach" @ Jack Hidary *downloaded*  ✅<br>
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <style>
            .hover-effect {
                position: relative;
                display: inline-block;
            }
            .hover-effect img {
                transition: transform 0.3s ease;
            }
            .hover-effect:hover img {
                transform: scale(1.1);
            }
            .hover-effect::after {
                content: attr(data-title);
                position: absolute;
                bottom: -100px;
                left: 100px;
                transform: translateX(-50%);
                background-color: #2A2436FF;
                color: white;
                padding: 5px 10px;
                border-radius: 5px;
                opacity: 0;
                transition: opacity 0.2s ease;
            }
            .hover-effect:hover::after {
                opacity: 1;
            }
        </style>
    </head>
    
    <a href="https://scienceadvantage.net/wp-content/uploads/2020/02/Quantum-Computing-An-Applied-Approach-2019-Year-.pdf" class="hover-effect" data-title="(https://scienceadvantage.net/wp-content/uploads/2020/02/Quantum-Computing-An-Applied-Approach-2019-Year-.pdf)">
        <img src="https://play-lh.googleusercontent.com/Bex_1KF_gXKkzhKGNr1-7Yr6akFdRFgeGS54-19sOfJVpTj0A--Km9C3euSdS6jbUg=s256-rw" alt="Quantum Computing: An Applied Approach" width="32">
    </a> 👉 Online

    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Quantum Computing Book</title>
        <style>
            .hover-effect {
                transition: transform 0.3s;
            }
            .hover-effect:hover {
                transform: scale(1.1);
            }
        </style>
    </head>
    <body>
        <a href="file:/home/opt/projects/oneom/books/Quantum-Computing-An-Applied-Approach-2019-Year-.pdf" class="hover-effect" data-title="Quantum-Computing-An-Applied-Approach-2019-Year-.pdf">
            <img src="https://play-lh.googleusercontent.com/Bex_1KF_gXKkzhKGNr1-7Yr6akFdRFgeGS54-19sOfJVpTj0A--Km9C3euSdS6jbUg=s256-rw" alt="Quantum Computing: An Applied Approach" width="32">
        </a>
    </body>
    </html> 👉 Local

#### Quantum Computing: An Applied Approach

    Contents
    Preface xi
    Acknowledgements xv
    Navigating this Book xvii

##### I Foundations

###### 1 Superposition, Entanglement and Reversibility.......................3

###### 2 A Brief History of Quantum Computing...............................11

###### 3 Qubits, Operators and Measurement..................................17
    3.1 Quantum Operators...................................................22
        Unary Operators.....................................................22
        Binary Operators....................................................26
        Ternary Operators...................................................28
    3.2 Comparison with Classical Gates.....................................30
    3.3 Universality of Quantum Operators...................................31
    3.4 Gottesman-Knill and Solovay-Kitaev..................................31
    3.5 The Bloch Sphere....................................................32
    3.6 The Measurement Postulate...........................................33

###### 4 Complexity Theory 37
    4.1 Problems vs. Algorithms.............................................37
    4.2 Time Complexity.....................................................38
    3.7 Computation-in-Place
    4.3 Complexity Classes..................................................40
    4.4 Quantum Computing and the Church-Turing Thesis......................43

##### II Hardware and Applications

###### 5 Building a Quantum Computer........................................47
    5.1 Assessing a Quantum Computer........................................47
    5.2 Neutral Atom........................................................49
    5.3 NMR.................................................................50
    5.4 NV Center-in-Diamond................................................51
    5.5 Photonics...........................................................52
    5.6 Spin Qubits.........................................................54
    5.7 Superconducting Qubits..............................................56
    5.8 Topological Quantum Computation.....................................57
    5.9 Trapped Ion.........................................................58
    5.10 Summary............................................................59

###### 6 Development Libraries for Quantum Computer Programming.............61
    6.1 Quantum Computers and QC Simulators.................................62
    6.2 Cirq................................................................64
    6.3 Qiskit..............................................................66
    6.4 Forest..............................................................69
    6.5 Quantum Development Kit.............................................71
    6.6 Dev Libraries Summary...............................................74
        Using the Libraries.................................................75
        Other Development Libraries.........................................75
    6.7 Additional Quantum Programs.........................................76
        Bell States.........................................................76
        Gates with Parameters...............................................77

###### 7 Teleportation, Superdense Coding and Bell’s Inequality.81
    7.1 Quantum Teleportation...............................................81
    7.2 Superdense Coding...................................................84
    7.3 Code for Quantum Teleportation and Superdense Communication.........85
    7.4 Bell Inequality Test................................................88

###### 8 The Canon: Code Walkthroughs.......................................95
    8.1 The Deutsch-Jozsa Algorithm.........................................97
    8.2 The Bernstein-Vazirani Algorithm...................................104
    8.3 Simon’s Problem....................................................107
    8.4 Quantum Fourier Transform..........................................108
    8.5 Shor’s Algorithm...................................................111
        RSA Cryptography...................................................111
        The Period of a Function...........................................113
        Period of a Function as an Input to a Factorization Algorithm......114
    8.6 Grover’s Search Algorithm..........................................126

###### 9 Quantum Computing Methods.........................................131
    9.1 Variational Quantum Eigensolver....................................131
        VQE with Noise.....................................................136
        More Sophisticated Ansatzes........................................138
    9.2 Quantum Chemistry..................................................139
    9.3 Quantum Approximate Optimization Algorithm (QAOA)..................144
        Example Implementation of QAOA.....................................147
    9.4 Machine Learning on Quantum Processors.............................154
    9.5 Quantum Phase Estimation...........................................160
       Implemention of QPE.................................................163
    9.6 Solving Linear Systems.............................................166
        Description of the HHL Algorithm...................................168
        Example Implementation of the HHL Algorithm........................170
    9.7 Quantum Random Number Generator....................................178
    9.8 Quantum Walks......................................................180
        Implementation of a Quantum Walk...................................182
    9.9 Summary............................................................187

###### 10 Applications and Quantum Supremacy...............................189
    10.1 Applications......................................................189
        Quantum Simulation and Chemistry...................................189
        Sampling from Probability Distributions............................190
        Linear Algebra Speedup with Quantum Computers......................190
        Optimization.......................................................190
        Tensor Networks....................................................190
    10.2 Quantum Supremacy.................................................190
        Random Circuit Sampling............................................191
        Other Problems for Demonstrating Quantum Supremacy.................195
    10.3 Future Directions.................................................196
        Quantum Error Correction...........................................196
        Doing Physics with Quantum Computers...............................197

##### III Toolkit

###### 11 Mathematical Tools for Quantum Computing I.......................201
    11.1 Introduction and Self-Test........................................201
    11.2 Linear Algebra....................................................203
        Vectors and Notation...............................................203
        Basic Vector Operations............................................204
        The Norm of a Vector...............................................208
        The Dot Product....................................................211
        Quantum Advantage
    11.3 The Complex Numbers and the Inner Product.........................214
        Complex Numbers....................................................214
        The Inner Product as a Refinement of the Dot Product...............216
        The Polar Coordinate Representation of a Complex Number............220
    11.4 A First Look at Matrices..........................................228
        Basic Matrix Operations............................................228
        The Identity Matrix................................................235
        Transpose, Conjugate and Trace.....................................237
        Matrix Exponentiation..............................................244
    11.5 The Outer Product and the Tensor Product..........................245
        The Outer Product as a Way of Building Matrices....................245
        The Tensor Product.................................................247
    11.6 Set Theory........................................................250
        The Basics of Set Theory...........................................250
        The Cartesian Product..............................................253
        Relations and Functions............................................254
        Important Properties of Functions..................................259
    11.7 The Definition of a Linear Transformation.........................264
    11.8 How to Build a Vector Space From Scratch..........................266
        Groups.............................................................267
        Fields.............................................................273
        The Definition of a Vector Space...................................280
        Subspaces..........................................................282
    11.9 Span, Linear Independence, Bases and Dimension....................285
        Span...............................................................285
        Linear Independence................................................287
        Bases and Dimension................................................289
        Orthonormal Bases..................................................292

###### 12 Mathematical Tools for Quantum Computing II......................295
    12.1 Linear Transformations as Matrices................................295
    12.2 Matrices as Operators.............................................300
        An Introduction to the Determinant.................................300
        The Geometry of the Determinant....................................305
        Matrix Inversion...................................................306
    12.3 Eigenvectors and Eigenvalues......................................314
        Change of Basis....................................................316
    12.4 Further Investigation of Inner Products...........................319
        The Kronecker Delta Function as an Inner Product...................322
    12.5 Hermitian Operators...............................................322
        Why We Can’t Measure with Complex Numbers..........................322
        Hermitian Operators Have Real Eigenvalues..........................324
    12.6 Unitary operators.................................................326
    12.7 The Direct Sum and the Tensor Product.............................327
        The Direct Sum.....................................................327
        The Tensor Product.................................................329
    12.8 Hilbert Space.....................................................333
        Metrics, Cauchy Sequences and Completeness.........................333
        An Axiomatic Definition of the Inner Product.......................337
        The Definition of Hilbert Space....................................338
    12.9 The Qubit as a Hilbert Space......................................339

###### 13 Mathematical Tools for Quantum Computing III.....................343
    13.1 Boolean Functions.................................................343
    13.2 Logarithms and Exponentials.......................................344
    13.3 Euler’s Formula...................................................346
    14 Table of Quantum Operators and Core Circuits........................349

##### Works Cited..........................................................353

##### Glossary and Notes --- Open Questions

Define quickly:
quantum teleportation
superdense coding

Quantum Sensing Applications: sensors for detecting position, navigation and timing (PNT) at the atomic scale. data when GPS is jammed or unavailable

##### References

- [ ] Feynman’s Lectures on Computation

---
### Videos

* (1/7) Qiskit YouTube playlist (PLOFEBzvs-Vvo...) *started* ✅
* Leonard Susskind — Stanford QM intro *started* ✅<br>
*  "Quantum Computing for Computer Scientists"<br>
<a href="https://www.youtube.com/watch?v=F_Riqjdh2oM" class="hover-effect" data-title="[Quantum Computing for Computer Scientists](https://www.youtube.com/watch?v=F_Riqjdh2oM)">
    <img src="https://images.icon-icons.com/17/PNG/256/social_youtube_2234.png" alt="Quantum Computing for Computer Scientists" width="32">
</a> 👉 Microsoft Research YouTube (1h, dense, excellent)

---
### Reference

* IBM Quantum Learning: learning.quantum.ibm.com *(remplace learning.qiskit.org)*  ✅
* <p style="margin-bottom: 0; margin-top: 0;">
    <h8 style="margin-top: 0rem;">Qiskit Textbook: <a href="qiskit.github.io/qiskit-textbook">qiskit.github.io/qiskit-textbook</a></h1>
</p>

---
### Hardware

* Node 1 — ASUS x550JK i5 12GB: dual boot Debian/Kali (VLM raté)<br>
  → Action: réinstaller Debian propre, dédier au compute<br>
* Node 2 — Lenovo B70-80 16GB: bureautique + IA<br>
  → Action: installer Qiskit ici en priorité<br>

---
### Software — Node 2

* Python 3.13.5 ✅
* Docker 29.3.0 ✅
* VS Codium 1.110.11631 ✅
* Venv OneOM dedie Jupyter: notebook qiskit qiskit-aer
* Extension ms-toolsai.Jupyternotebook installee dans VSCodium

---

## Cheat Sheet

---
### Decomposition Matricielle

+ Polynome caracteristique $det(A-\lambda I)$
+ Resoudre avec $\lambda = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$
+ On obtient les valeurs propres $\lambda_1$ et $\lambda_2$
+ Matrice des valeurs propres: 
$
\begin{pmatrix} 
\lambda_1 \\ 
\lambda_2 
\end{pmatrix} \cdot 
\begin{pmatrix} 
1 & 0 \\ 
0 & 1 
\end{pmatrix} = 
\begin{pmatrix} 
\lambda_1   & 0 \\ 
0           & \lambda_2 
\end{pmatrix}$
+ Chaque valeur propre verfifie ensuite: 
$
    ( \begin{pmatrix} 
        A_{11}  & A_{12} \\ 
        A_{21}  & A_{22} 
    \end{pmatrix} - 
        \begin{pmatrix} 
            \lambda_1 \\ 
            \lambda_2 
        \end{pmatrix} \cdot 
            \begin{pmatrix} 
                1   & 0 \\ 
                0   & 1 
            \end{pmatrix} ) \cdot 
                \begin{pmatrix} 
                    v_{1} \\ 
                    v_{2} 
                \end{pmatrix} = 
    0
$
+ On propose dans chaque cas le vecteur propre avec $v_1=1$ et $v_2$ correspondant
+ $P$ matrice des vecteurs propres en colonnes
+ $D$ vecteur des valeurs propres multiplie par matrice identite
+ $
    P^{-1} = 
    \frac{1} {\text{det}(P)} \cdot 
        \begin{pmatrix} 
            d   & -b \\ 
            -c  & a 
        \end{pmatrix}
$
+ Calculer $PDP^{-1}$

---
### Logs

The expression $\log_3(2)$ is called a logarithm with base 3 of 2. It answers the question: **"To what power must 3 be raised to get 2?"**

___
#### What is $\log_b(a)$?

In general, $\log_b(a)$ means:
**"The exponent to which $b$ must be raised to obtain $a$."**

So, $\log_3(2)$ is the number $y$ such that:
$3^y = 2$

___
#### Change of Base Formula

The change of base formula allows you to rewrite a logarithm in terms of natural logarithms (or any other base):
$ 
    \log_b(a) = 
    \frac{\ln(a)} {\ln(b)} 
$

So, in your problem:
$ 
    x = 
    \frac{100 \ln(2)} {\ln(3)} = 
    100 \log_3(2)
$

This means you can express the solution using either natural logarithms or the logarithm with base 3 of 2.

___
#### Why is this useful?

- It allows you to compute logarithms with any base using a calculator (which usually only has $\ln$ or $\log_{10}$).
- It simplifies expressions and makes them easier to interpret.

---

## Comments

Stern Gerlach: measurements
David Wallace calls it “the emergent multiverse”

* mkdir -p /home/opt/projects/oneom/prod/{circuits,algorithms,notes} ✅ ▶️ 'quantum' est devenu 'prod' pour plus de clarte 💡
* alias oneom='source $QENV/bin/activate && jupyter notebook'
* $ |\psi\rangle = \alpha|↑\rangle + \beta|→\rangle $ ↓ ←
