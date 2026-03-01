## Facts
- 3 DC Kafka 4.1 deployment with cp-ansible
- Airgapped environment, everything must be ready beforehand (prometheus, ansible, etc)
- Staging (1 cluster) and Prod (2.5 cluster) setup
- Proposed prod setup
	- DC1 (3 brokers, 3 KRaft)
	- DC2 (3 brokers, 3 KRaft)
	- DC3 (3 bokers, 3 KRaft)
- mTLS based authentication
- cp-ansible 8.0 onwards requires Python 3.10 on all nodes (previously 3.6)

## Procedural
- For production start with single DC deployment first
- Always ping ansible first
	- `ansible -m ping -i <inventory> all -kK`
	- `-kK` needed if password required (`-k` for ssh, `-K` for sudo)

## Conceptual
- With even number of KRaft we can still encounter split brain (unlikely but possible)
- Hence starting with 1 KRaft on DC1 is the safest but at the cost of no HA
- For stretch cluster must use rack id + rack aware selector
	- RF=6 (ensure 3 copies on each DC) - this is a fallback, always use topic placement constraint
	- MIR=4 (formula: RF/2+1)

## Questions
-

## Logs
### [[2026-02-24]]
- VM memory upgraded
- Brokers and KRaft running
- mTLS set

### [[2025-12-03]]
- Python 3.12 installed first
- Deployment done on a separate ansible server
- Ansible collection installed at `/usr/share/ansible/collections/ansible_collections`
	- Modified ansible.cfg to add collection path and `host_key_checking=False`
- Deployed plaintext deployment successfully

### [[2025-09-26]]
- Fixed tmpdir issue using `kafka_broker_custom_java_args`
- For stretch cluster
	- Need rack id + rack aware selector
	- Topic placement config (do this after everything is set up) — for internal topics and future topics
- Successfully deployed in staging for plaintext/non-certificate version
- Important steps
	- Manually install pip + pip cryptography
		- Remove python 3.6 (yum)
		- Install python 3.12 (yum)
		- Install python 3.12 cryptography (yum)
	- Then run ansible playbook skipping pip-package tag
	- Ensure `/opt/kafka` has correct user + group

### [[2025-09-19]]
- New Kafka cluster, airgapped installation
- Kafka 4.1 with 3 DC planned
- mTLS required
- RBAC vs ACL — client unfamiliar with the difference
- Self balancing cluster
	- Set default placement constraint on broker (many initial topics ignore it)
	- Self balancing detects changes ~30min after broker restart
- Observer
	- Follows leader but won't join ISR unless ISR goes offline and promotes observer
	- `kafka-topics --describe` will show observer status
