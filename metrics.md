# Lean Metrics

- [Node Info Metrics](#node-info-metrics)
- [PQ Signature Metrics](#pq-signature-metrics)
- [Block Production Metrics](#block-production-metrics)
- [Fork-Choice Metrics](#fork-choice-metrics)
- [State Transition Metrics](#state-transition-metrics)
- [Validator Metrics](#validator-metrics)
- [Network Metrics](#network-metrics)

## Node Info Metrics

| Name   | Type  | Usage | Sample collection event | Labels | EthLambda | Grandine | Lantern  | Lighthouse | Qlean    | Ream     | Zeam     |
|--------|-------|-------|-------------------------|--------|-----------|----------|----------|------------|----------|----------|----------|
| `lean_node_info` | Gauge | Node information (always 1) | On node start | name, version | □ | □ | □ | □ | □ | □ | □ |
| `lean_node_start_time_seconds` | Gauge | Start timestamp | On node start | | □ | □ | □ | □ | □ | □ | □ |


## PQ Signature Metrics

| Name   | Type  | Usage | Sample collection event | Labels | Buckets | EthLambda | Grandine | Lantern  | Lighthouse | Qlean    | Ream     | Zeam     |
|--------|-------|-------|-------------------------|--------|---------|-----------|----------|----------|------------|----------|----------|----------|
| `lean_pq_sig_attestation_signatures_total` | Counter | Total number of individual attestation signatures | On each attestation signing | | | □ | □ | □ | □ | □ | □ | □ |
| `lean_pq_sig_attestation_signatures_valid_total`| Counter | Total number of valid individual attestation signatures | On each attestation signature verification | | | □ | □ | □ | □ | □ | □ | □ |
| `lean_pq_sig_attestation_signatures_invalid_total`| Counter | Total number of invalid individual attestation signatures | On each attestation signature verification | | | □ | □ | □ | □ | □ | □ | □ |
| `lean_pq_sig_attestation_signing_time_seconds` | Histogram | Time taken to sign an attestation | On each attestation signing | | 0.005, 0.01, 0.025, 0.05, 0.1, 1 | □ | □ | □ | □ | □ | □ | □ |
| `lean_pq_sig_attestation_verification_time_seconds` | Histogram | Time taken to verify an attestation signature | On each attestation signature verification | | 0.005, 0.01, 0.025, 0.05, 0.1, 1 | □ | □ | □ | □ | □ | □ | □ |
| `lean_pq_sig_aggregated_signatures_total` | Counter | Total number of aggregated signatures | On aggregated signature production | | | □ | □ | □ | □ | □ | □ | □ |
| `lean_pq_sig_aggregated_signatures_valid_total`| Counter | Total number of valid aggregated signatures | On aggregated signature verification | | | □ | □ | □ | □ | □ | □ | □ |
| `lean_pq_sig_aggregated_signatures_invalid_total`| Counter | Total number of invalid aggregated signatures | On aggregated signature verification | | | □ | □ | □ | □ | □ | □ | □ |
| `lean_pq_sig_attestations_in_aggregated_signatures_total` | Counter | Total number of attestations included into aggregated signatures | On aggregated signature production | | | □ | □ | □ | □ | □ | □ | □ |
| `lean_pq_sig_aggregated_signatures_building_time_seconds` | Histogram | Time taken to build an aggregated attestation signature | On aggregated signature production | | 0.1, 0.25, 0.5, 0.75, 1, 1.25, 1.5, 2, 4 | □ | □ | □ | □ | □ | □ | □ |
| `lean_pq_sig_aggregated_signatures_verification_time_seconds` | Histogram | Time taken to verify an aggregated attestation signature | On aggregated signature verification | | 0.1, 0.25, 0.5, 0.75, 1, 1.25, 1.5, 2, 4 | □ | □ | □ | □ | □ | □ | □ |

## Block Production Metrics

| Name   | Type  | Usage | Sample collection event | Labels | Buckets | EthLambda | Grandine | Lantern  | Lighthouse | Qlean    | Ream     | Zeam     |
|--------|-------|-------|-------------------------|--------|---------|-----------|----------|----------|------------|----------|----------|----------|
| `lean_block_aggregated_payloads` | Histogram | Number of `aggregated_payloads` in a block | On block production | | 1, 2, 4, 8, 16, 32, 64, 128 | □ | □ | □ | □ | □ | □ | □ |
| `lean_block_building_payload_aggregation_time_seconds` | Histogram | Time taken to build `aggregated_payloads` during block building | On block production | | 0.1, 0.25, 0.5, 0.75, 1, 2, 3, 4 | □ | □ | □ | □ | □ | □ | □ |
| `lean_block_building_time_seconds` | Histogram | Time taken to build a block | On block production | | 0.01, 0.025, 0.05, 0.1, 0.25, 0.5, 0.75, 1 | □ | □ | □ | □ | □ | □ | □ |
| `lean_block_building_success_total` | Counter | Successful block builds | On block production | | | □ | □ | □ | □ | □ | □ | □ |
| `lean_block_building_failures_total` | Counter | Failed block builds (exception in build_block) | On block production failure | | | □ | □ | □ | □ | □ | □ | □ |
|

## Fork-Choice Metrics

| Name   | Type  | Usage | Sample collection event | Labels | Buckets | EthLambda | Grandine | Lantern  | Lighthouse | Qlean    | Ream     | Zeam     |
|--------|-------|-------|-------------------------|--------|---------|-----------|----------|----------|------------|----------|----------|----------|
| `lean_head_slot` | Gauge | Latest slot of the lean chain | On get fork choice head | | | □ | □ | ✅  | □ | ✅ | ✅ | ✅ |
| `lean_current_slot` | Gauge | Current slot of the lean chain | On scrape | | | □ | □ | □ | □ | □ | □ | □ |
| `lean_safe_target_slot` | Gauge | Safe target slot | On safe target update | | | □ | □ | □ | □ | □ | □ | □ |
|`lean_fork_choice_block_processing_time_seconds`| Histogram | Time taken to process block | On fork choice process block | | 0.005, 0.01, 0.025, 0.05, 0.1, 1, 1.25, 1.5, 2, 4 | □ | □ | ✅ | □ | ✅ | ✅ | □ |
| `lean_attestations_valid_total`| Counter | Total number of valid attestations | On validate attestation | | | □ | □ | ✅ | □ | ✅ | ✅ | □ |
| `lean_attestations_invalid_total`| Counter | Total number of invalid attestations | On validate attestation | | | □ | □ | ✅ | □ | ✅ | ✅ | □ |
| `lean_attestation_validation_time_seconds`| Histogram | Time taken to validate attestation | On validate attestation | | 0.005, 0.01, 0.025, 0.05, 0.1, 1 | □ | □ | ✅ | □ | ✅ | ✅ | □ |
| `lean_fork_choice_reorgs_total` | Counter | Total number of fork choice reorgs | On fork choice reorg | | | □ | □ | □ | □ | □ | □ | □ |
| `lean_fork_choice_reorg_depth` | Histogram | Depth of fork choice reorgs (in blocks) | On fork choice reorg | | 1, 2, 3, 5, 7, 10, 20, 30, 50, 100 | □ | □ | □ | □ | □ | □ | □ |
| `lean_gossip_signatures` | Gauge | Number of gossip signatures in fork-choice store | On gossip signatures update | | | □ | □ | □ | □ | □ | □ | □ |
| `lean_latest_new_aggregated_payloads` | Gauge | Number of new aggregated payload items | On `latest_new_aggregated_payloads` update | | | □ | □ | □ | □ | □ | □ | □ |
| `lean_latest_known_aggregated_payloads` | Gauge | Number of known aggregated payload items | On `latest_known_aggregated_payloads` update | | | □ | □ | □ | □ | □ | □ | □ |
| `lean_committee_signatures_aggregation_time_seconds` | Histogram | Time taken to aggregate committee signatures | On committee signatures aggregation | | 0.05, 0.1, 0.25, 0.5, 0.75, 
  1, 2, 3, 4 | □ | □ | □ | □ | □ | □ | □ |
| `lean_node_sync_status` | Gauge | Node sync status | On node sync status change | status=idle,syncing,synced | | □ | □ | □ | □ | □ | □ | □ |

## State Transition Metrics

| Name   | Type  | Usage | Sample collection event | Labels | Buckets | EthLambda | Grandine | Lantern  | Lighthouse | Qlean    | Ream     | Zeam     |
|--------|-------|-------|-------------------------|--------|---------|-----------|----------|----------|------------|----------|----------|----------|
| `lean_latest_justified_slot` | Gauge | Latest justified slot | On state transition | | | □ | □ | ✅ | □ | ✅ | ✅ | ✅ |
| `lean_latest_finalized_slot` | Gauge | Latest finalized slot | On state transition | | | □ | □ | ✅ | □ | ✅ | ✅ | ✅ |
| `lean_finalizations_total` | Counter | Total number of finalization attempts | On finalization attempt | result=success,error | | □ | □ | □ | □ | □ | □ | □ |
| `lean_state_transition_time_seconds` | Histogram | Time to process state transition | On state transition | | 0.25, 0.5, 0.75, 1, 1.25, 1.5, 2, 2.5, 3, 4 | □ | □ | ✅ | □ | ✅ | ✅ | ✅ |
| `lean_state_transition_slots_processed_total` | Counter | Total number of processed slots | On state transition process slots | | | □ | □ | ✅ | □ | ✅ | ✅ | ✅ |
| `lean_state_transition_slots_processing_time_seconds` | Histogram | Time taken to process slots | On state transition process slots | | 0.005, 0.01, 0.025, 0.05, 0.1, 1 | □ | □ | ✅ | □ | ✅ | ✅ | ✅ |
| `lean_state_transition_block_processing_time_seconds` | Histogram | Time taken to process block | On state transition process block | | 0.005, 0.01, 0.025, 0.05, 0.1, 1 | □ | □ | ✅ | □  | ✅ | ✅ | ✅ |
| `lean_state_transition_attestations_processed_total` | Counter | Total number of processed attestations | On state transition process attestations | | | □ | □ | ✅ | □ | ✅ | ✅ | ✅ |
| `lean_state_transition_attestations_processing_time_seconds` | Histogram | Time taken to process attestations | On state transition process attestations | | 0.005, 0.01, 0.025, 0.05, 0.1, 1 | □ | □ | ✅ | □ | ✅ | ✅ | ✅ |

## Validator Metrics

| Name   | Type  | Usage | Sample collection event | Labels | EthLambda | Grandine | Lantern  | Lighthouse | Qlean    | Ream     | Zeam     |
|--------|-------|-------|-------------------------|--------|-----------|----------|----------|------------|----------|----------|----------|
|`lean_validators_count`| Gauge | Number of validators managed by a node | On scrape |  | □ | □ | ✅ | □ | ✅ | ✅ | ✅ |
|`lean_is_aggregator`| Gauge | Validator's `is_aggregator` status. True=1, False=0 | On node start |  | □ | □ | □ | □ | □ | □ | □ |

## Network Metrics

| Name   | Type  | Usage | Sample collection event | Labels | Buckets | EthLambda | Grandine | Lantern  | Lighthouse | Qlean    | Ream     | Zeam     |
|--------|-------|-------|-------------------------|--------|---------|-----------|----------|----------|------------|----------|----------|----------|
| `lean_connected_peers` | Gauge | Number of connected peers | On scrape | client=ethlambda,grandine,lantern,lighthouse,qlean,ream,zeam | | □ | □ | □ | □ | 📝 | ✅ | □ |
| `lean_peer_connection_events_total` | Counter | Total number of peer connection events | On peer connection | direction=inbound,outbound<br>result=success,timeout,error | | □ | □ | □ | □ | □ | 📝 | □ |
| `lean_peer_disconnection_events_total` | Counter | Total number of peer disconnection events | On peer disconnection | direction=inbound,outbound<br>reason=timeout,remote_close,local_close,error | | □ | □ | □ | □ | □ | 📝 | □ |
| `lean_attestation_committee_subnet` | Gauge | Node's attestation committee subnet | On node start | | | □ | □ | □ | □ | □ | □ | □ |
| `lean_attestation_committee_count` | Gauge | Number of attestation committees (ATTESTATION_COMMITTEE_COUNT) | On node start | | | □ | □ | □ | □ | □ | □ | □ |
| `lean_gossip_block_size_bytes` | Histogram | Bytes size of a gossip block message | On gossip block received | | 10000, 50000, 100000, 250000, 500000, 1000000, 2000000, 5000000 | □ | □ | □ | □ | □ | □ | □ |
| `lean_gossip_attestation_size_bytes` | Histogram | Bytes size of a gossip attestation message | On gossip attestation received | | 512, 1024, 2048, 4096, 8192, 16384 | □ | □ | □ | □ | □ | □ | □ |
| `lean_gossip_aggregation_size_bytes` | Histogram | Bytes size of a gossip aggregated attestation message | On gossip aggregate_and_proof received | | 1024, 4096, 16384, 65536, 131072, 262144, 524288, 1048576 | □ | □ | □ | □ | □ | □ | □ |
