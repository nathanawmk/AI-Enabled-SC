# Artificial Intelligence Enabled Smart Contracts. AI-Enabled Smart Contracts: Self-Learning Smart Contracts 
Nathan M.K. Aw 

nathan.mk.aw@gmail.com

# Abstract.
At first glance, AI-Enabled Smart Contracts seems to be an oxymoron -- A smart contract is a set of promises, specified in digital form which necessitates that its behaviour/outcome is bounded based on input conditions. (A parallel to draw will be a java method that takes in two input and does a multiplication and/or a deterministic consensus algorithm.) AI, however, denotes human like behaviour/outcome which is unbounded. 

This paper seeks to bridge the gap. This paper will systematically and rigorously define how smart contract and its function can be "AI-Enabled" and/or "AI Enhanced".  

This paper also explores in detail the possible applications and wide-ranging usage of Artificial Intelligence (AI) in Smart Contracts (SC) in different industries. It also explores self-learning capabilities within smart contracts that learns from its inputs while at the same time adhering to contractual clauses. Reference Implementation based on AI Framework (E.g., Tensor Flow) and Solidity is ongoing and is expected to be released in Q4 2018. 

Note: This paper is not a rehash or extension of "Plasma: Scalable Autonomous Smart Contracts" (https://plasma.io/). For example, this paper does not address scalability concerns. 

Ethereum is a transaction-based state machine. A valid state transition is one which comes about through a transaction. Formally:
(1) σt+1 ≡ Υ(σt, T)

Before one can explore how smart contracts be AI-enabled, one needs to first take a look at an ethereum-based smart contract written in solidity (https://www.ethereum.org/greeter):

contract mortal {
    /* Define variable owner of the type address */
    address owner;

    /* This function is executed at initialization and sets the owner of the contract */
    function mortal() { owner = msg.sender; }

    /* Function to recover the funds on the contract */
    function kill() { if (msg.sender == owner) selfdestruct(owner); }
}

contract greeter is mortal {
    /* Define variable greeting of the type string */
    string greeting;
    
    /* This runs when the contract is executed */
    function greeter(string _greeting) public {
        greeting = _greeting;
    }

    /* Main function */
    function greet() constant returns (string) {
        return greeting;
    }
}


SOURCE: https://www.ethereum.org/greeter
