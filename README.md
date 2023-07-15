# Substrate Prover Service

The Substrate prover is an offchain, long-running service whose primary responsibility is to prove arbitrary programs which are stored onchain. This one expects to be paired with a Substrate chain which has a specific pallet, `prover_mgmt`. The substrate node, including runtime and pallets lives in `./node`.

The prover listens for the ProofRequested event emitted from the `prover_mgmt` pallet. If received, it takes any arguments passed to it and starts to prove the requested image id. Once done, it should call back to the pallet with the image id and the proof. The prover lives in `./prover`.

# Running

## Start local node
`cargo build --release`

## Start Proving service
`cd prover`
`cargo build --release`
