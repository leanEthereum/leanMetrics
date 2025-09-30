# Lean Metrics

- [Fork-Choice Metrics](#fork-choice-metrics)
- [State Transition Metrics](#state-transition-metrics)
- [Validator Metrics](#validator-metrics)
- [Network Metrics](#network-metrics)


## Fork-Choice Metrics

| Name   | Type  | Usage | Sample collection event | Labels | Buckets | Qlean    | Ream     | Zeam     |
|--------|-------|-------|-------------------------|--------|---------|----------|----------|----------|
| `lean_head_slot` | Gauge | Latest slot of the beacon chain | On get fork choice head | | | □ | □ | □ |
|`lean_fork_choice_block_processing_time_seconds`| Histogram | Time taken to process block | On fork choice process block | | 0.005, 0.01, 0.02, 0.05, 0.1, 1 | □ | □ | □ |
|`lean_attestations_validated_total`| Counter | Total number of valid attestations | On validate attestation | result: valid, invalid | | □ | □ | □ |
|`lean_attestation_validation_time_seconds`| Counter | Time taken to validate attestation | On validate attestation | | 0.05, 0.1, 0.5, 1, 1.5, 2, 2.5, 3, 4 | □ | □ | □ |

## State Transition Metrics

| Name   | Type  | Usage | Sample collection event | Labels | Buckets | Qlean    | Ream     | Zeam     |
|--------|-------|-------|-------------------------|--------|---------|----------|----------|----------|
| `lean_latest_justified_slot` | Gauge | Latest justified slot | On state transition | | | □ | □ | □ |
| `lean_latest_finalized_slot` | Gauge | Latest finalized slot | On state transition | | | □ | □ | □ |
|`lean_state_transition_time_seconds`| Histogram | Time to process state transition | On state transition | | 0.2, 0.5, 0.75, 1, 1.25, 1.5, 2, 2.5, 3, 10 | □ | □ | □ |
|`lean_state_transition_slots_processed_total`| Counter | Processed slots | On state transition process slots | | | □ | □ | □ |
|`lean_state_transition_slots_processing_time_seconds`| Histogram | Time taken to process slots | On state transition process slots | | 0.005, 0.01, 0.02, 0.05, 0.1, 1 | □ | □ | □ |
|`lean_state_transition_block_processing_time_seconds`| Histogram | Time taken to process block | On state transition process block | | 0.005, 0.01, 0.02, 0.05, 0.1, 1 | □ | □ | □ |
|`lean_state_transition_attestations_processed_total`| Counter | Total number of processed attestations | On state transition process attestations | | | □ | □ | □ |
|`lean_state_transition_attestations_processing_time_seconds`| Counter | Time taken to process attestations | On state transition process attestations | | 0.2, 0.5, 0.75, 1, 1.25, 1.5, 2, 2.5, 3, 10 | □ | □ | □ |

## Validator Metrics

| Name   | Type  | Usage | Sample collection event | Labels | Qlean    | Ream     | Zeam     |
|--------|-------|-------|-------------------------|--------|----------|----------|----------|
|`lean_active_validators_count`| Gauge | Number of active validators | On scrape | client: {client_name} | □ | □ | □ |

## Network Metrics

| Name   | Type  | Usage | Sample collection event | Labels | Qlean    | Ream     | Zeam     |
|--------|-------|-------|-------------------------|--------|----------|----------|----------|
|`lean_mesh_peers_by_client_count`| Gauge | Number of mesh peers by clients | On scrape | client: {client_name} | □ | □ | □ |
