# Traffic Classification and Shaping

### Ways to classify traffic

* Classification of sources
  * Data: bursty, periodic, regular
  * Audio: continuous, periodic
  * Video: continuous, bursty, periodic
* Two Classes
  1. CBR (Constant BitRate)
    * traffic arrives at regular intervals with same packet sizes
    * Audio
    * Shaped according to peak rate
  2. VBR (Variable BitRate)
    * traffic arrives at variable intervals
    * Video, data
    * Shaped according to average rate

### Traffic Shaping approaches

1. Leaky Bucket - one bucket per flow
  * Data arrives in bucket of size B
  * p = drain rate
  * Max avg rate is p
  * regulator at bottom of bucket makes sure burst doesnt exceed bucket size
    * Audio:
      * B = 16kb
      * packet size = 1kb
        * can accumulate a burst of 16 packets in the bucket
      * p = 8 packets per sec (avg)
        * ensures that rate is smoothed to avg rate not to exceed 8KBps
2.  (r,T) Traffic Shaping
  * traffic divided into T-bit frames.
  * Flow can inject ≤ r bits in any T-bit frame
  * (r,T) smooth
  * flow can send excess data in bits instead of packets 
  * priorities can be set by sender or network
3.Token Bucket - Shaping Bursty Traffic Patterns
  * B = bucket size
  * p = rate at which tokens are placed in bucket
  * traffic can be sent by regulator as long as there are tokens in B
  * packet size b < B
  * if B is full, Packet is sent and b tokens are removed
  * if B is empty, packet must wait until b tokens arrive
  * if partially full:
    * if < b packets in B, packet has to wait
    * if ≥ b packets in B, packet is sent

## Token Bucket vs. Leaky Bucket

![tokenvsleaky](images/tvl.png)

* Policing with Token Buckets (Composite Shaper)
  * combining leaky bucket and token buckets
  * smooths traffic, but requires 2 counters
