## More advanced EC2 topics

### Placement groups
Placement groups determine how the underlying EC2 instances are placed on the underlying aws hardware to optimize performance or availability.

There are **3 types**:

1. **Cluster Placement Group**
- Instances are placed close together within a single AZ.
- Low latency, high throughput networking.
- Ideal for applications requiring fast communication between instances.
  
**Use cases**: HPC (High Performance Computing), tightly coupled workloads, high-speed data processing.

**Risk**: Greater impact if the underlying hardware or placement fails.

2. **Spread Placement Group**
- Instances are placed on distinct underlying hardware.
- Reduces chances of single point of failure.
- Can span multiple Availability Zones (AZ) in a single region.
- Limited to 7 instances per AZ per placement group.

**Use cases**: Critical applications, small groups of instances requiring hardware isolation.

3. **Partition Placement Groups**
- Instances are distributed across multiple logical partitions.
- Each partition has separate racks and hardware.
- A hardware failure in one partition does not affect the other partitions.
- Can span multiple AZs within a single region.
- Supports large distributed workloads.
- To know which partition the instances are on, we can make use of the metadata.

**Use cases**: Hadoop, Cassandra, Kafka, distributed big-data applications.

4. **Precision Time**
- direct access to high-precision time sources.
- Give more accurate timings than Npt.

**Hands-on**:
- **Creating Group**: EC2 -> Placement Groups -> Create Placement Groups -> Name it -> Select the Placement Group type -> Choose special configurations for the individual group if required -> Create Group

- **Applying Group**: Create Instance -> Advance Settings -> Placement groups -> Select appropriate group



