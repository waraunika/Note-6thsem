- **5 Hours**
- **8 Marks**
# For Assessment
1. Compose 4Kx16 ROM using 1Kx8 ROMs. [[#Example 3 Compose 1 K x 8 ROMs into a 4K x 16 ROM]]
2. Explain storage permanence of memory. [[#Storage Permanence]]
3. Explain fully associative cache mapping technique [[#B.i.b Fully Associative mapping]]
4. Explain replacement algorithms used in cache memory. [[#4.B.ii Cache-Replacement Policy]]
# 4.1 Memory Write Ability and Storage Permanence
## Memory Write Ability
- Write Ability refers to the manner and speed that a particular memory can be written.
- Every memory must have a way to write bits onto it but the manner and speed of such writing varies among different memory.
- In-system programmable is used to categorize memories into two along the write ability axis.
- In-system programmable memory can be programmed by a processor whereas non in-system programmable memory must be programmed by some external means.
- Range of Write Ability 
	- High End 
		- processor can write to memory simply and quickly by setting its address lines, data input bits and control lines appropriately.
		- Example: RAM
	- Middle Range
		- processor can write to memory a bit slower compared to high end.
		- Example: EEPROM, FLASH 
	- Lower Range
		- special device called programmer is used to write into the memory
		- The device must apply suitable voltage levels to write to the memory.
		- E.g.: EPROM, OTP ROM
	- Low End
		- bits are stored during fabrication
		- Example: Mask-programmed ROM
		- 
## Storage Permanence
- refers to the ability of a memory device to retain its stored data (bits) after those bits have been written. 
- It is a fundamental characteristic that determines how and where a particular memory type can be used in an embedded system.
- Memory types are primarily divided into two broad categories along the storage permanence axis:
	- **Non-Volatile Memory (NVM):** Can hold its stored bits even after power is no longer supplied to the device. The data persists through power cycles.
	- **Volatile Memory (VM):** Requires continuous power to retain its data. Once power is removed, the stored information is lost.
- However, storage permanence is not simply a binary "yes" or "no" property. It exists on a spectrum, or **range**, from bits that fade almost instantly to those that last forever (or until the chip is destroyed).
### The Spectrum of Storage Permanence
#### 1. Low End: The Refresh Required Tier
- **Behavior:** Memory at this end of the spectrum begins to lose its stored bits almost immediately after they are written. To retain data, the memory must be constantly and periodically **refreshed** (read and rewritten).
- **Characteristics:**
    - High density (can store a lot of data in a small area).
    - Low cost per bit.
    - High power consumption due to the constant refresh cycles.
- **Example:** **Dynamic RAM (DRAM)** . Used as the main memory (RAM) in computers, where its high density and low cost are essential, and a dedicated memory controller handles the constant refresh.
#### 2. Lower Range: The Power-On Dependent Tier
- **Behavior:** Memory in this range holds its bits perfectly and indefinitely, but **only as long as power is continuously applied to the memory chip**. The moment power is cut, the data vanishes.
- **Characteristics:**
    - Very fast read and write speeds.
    - No need for a complex refresh controller.
    - Requires more transistors per bit than DRAM, making it less dense and more expensive.
- **Example:** **Static RAM (SRAM)** . Used for processor caches (L1, L2, L3) where speed is paramount, and the system knows the data is only needed while the power is on.
#### 3. Middle Range: The Long-Term Retention Tier
- **Behavior:** This category bridges the gap between volatile and non-volatile. Memory here can hold its bits for an extended period, days, months, or even years, **after the memory's power source has been turned off**.
- **Characteristics:**
    - Offers the key benefit of non-volatility: data persists through power cycles.
    - Write speeds are generally slower than volatile memory and may have a limited number of write cycles.
- **Example:** **Non-Volatile RAM (NVRAM)** , which often refers to technologies like **Flash memory**, **EEPROM**, or battery-backed SRAM. Used in USB drives, SSDs, and firmware storage (BIOS/UEFI).
#### 4. High End: The Permanent Tier
- **Behavior:** Memory at this end is truly permanent. It will never lose its stored bits, regardless of power, and will retain the data for the entire lifespan of the chip, provided the chip itself is not physically damaged.
- **Characteristics:**
    - Extremely stable and reliable.
    - The data is written during the manufacturing process and cannot be altered (or is very difficult to alter) by the end-user.
- **Example:** **Mask-Programmed Read-Only Memory (Mask ROM)** . Used for mass-produced devices where the firmware is absolutely final and will never need an update, such as in some older appliances or for immutable boot code.
---
# 4.2 Common Memory Types
# 4.3 Composing Memory
- composing memory is needed when there is a need of particular-sized memory, which is not readily available.
- if the available memory is larger than required one
	- then we simply use the needed lower words of the memory and ignore the higher words which are not required.
- however, if the available memory is smaller than needed, some more design procedures are needed to be followed.
- various cases for composing memory have been discussed in the following paragraphs.
## 4.3.A Case 1: to increase the width of words.
- when the number of words in the available memory is same to that of required one but the number of bits or width of word is not enough then the width must be increased.
- to do that, the available memories are connected side by side as shown in the given example.
### Example 1: Compose 1K x 8 ROMs into 1K x 32 ROM
- the available ROM 1K x 8 and required ROM of 1K x 32 have same number of words
- but width is different.
- number of ROM to be placed side by side is given by n.
	- n = width of required ROM/width of available ROM = 32/8 = 4
	- address line = 1K = 1024 bytes = 2$^{10}$ = 10 address lines
	- data line = 8 lines
- hence four 1 k x 8 ROMs are placed side by side to compose 1K x 32.
- figure:
	- ![[Pasted image 20260224160500.png]]
## 4.3.B Case 2: To increase the number of words
- when the width of the word in the available memory and required memory is same but the number of words are different, then the words must be increased.
- we connect the ROMs top to bottom and data line of each ROM is ORed.
- Since the number of words has to be increased, extra high-order address is required to select the particular ROM which can be implemented by using appropriate decoder.
### Example 2: Compose 1K x 8 ROMs into a 4K x 8 ROM
- The available ROM 1K x 8 and required ROM 4k x 8 have width of 8 bits but the number of words is different.
- Number of ROMs and size of decoder can be determined as
	- N = number of words in required ROM / number of words in available ROM = 4k / 1k = 4
	- Decoder : it must be select 4 ROM, so 2 x 4 decoder must be used.
	- Higher address bits: log$_2$(4K) - log$_2$(1K) = log$_2$(2$^{12}$) - log$_2$(2$^{10}$) = 12 - 10 = 2 bits or lines
	- total address line: 4K = 2$^{12}$ = 12 address lines, and 10 lines (A$_9$ to A$_0$) are connected to each ROM.
	- 2 higher address is represented by inputs of decoder.
- hence four roms must be connected top to bottom and data line of each ROM is ORed.
- Decoder of 2 x 4 is used to select a particular ROM.
- figure:
	- ![[Pasted image 20260224161117.png]]
## 4.3.C Case 3 To increase both, number of words and word width
- when the width of the word as well as the number of words in the available memory and required memory are different then the technique used in case 1 and case 2 must be combined.
- initially, the number of words is increased and then the top-bottom set of ROMs with ORed data lines are placed side by side to increase the word width.
### Example 3: Compose 1 K x 8 ROMs into a 4K x 16 ROM
- the available ROM 1k x 8 and required ROM 4k x 16 differ in number of words as well as word width
	- increase number of words:
		- 4k / 1k = 4, four roms are required with 2 x 4 decoder.
		- 4k represents 12 address lines
		- 10 lines connected to every ROM and 2 lines represented by inputs of decoder
	- increase word width
		- 16/8 = 2
		- four sets of ROMs are repeated two times and placed side by side.
- figure:
	- ![[Pasted image 20260224162535.png]]
# 4.4 Memory Hierarchy and Cache
## 4.4.A Memory Hierarchy
- A system cannot be implemented with only fast memory as it makes the system very expensive.
- also the use of only slow and low cost memory will make system very inefficient
- so, the concept of memory hierarchy comes into action in which a system is more likely to implement slow but high capacity memory for storage along with fast but small memory for high speed processing.
- memory hierarchy defines the level of memory based on cast per bit, capacity and access time
- as we move down the hierarchy, capacity increases, access time increases and cost per time decreases.
- figure:
	- ![[Pasted image 20260224162810.png]]
## 4.4.B Cache Memory
- cache is a small but fast memory which contains a copy of portions of main memory to expedite operations of the system.
- Cache is designed using static RAM which makes it faster as compared to main memory.
- the access time for cache can get low as one clock cycle while main memory access requires several cycles.
- So, the instructions and data which are supposed to get accessed frequently are placed in cache memory.
- Hence the average access time is reduced resulting in improved performance.
- During cache operation, the processor first checks the required word in cache.
- if it is available (cache hit), the word is delivered to the processor.
- but if the word is not available (cache miss) in cache then the corresponding block of main memory is read into cache.
- and finally the word is made available to the process.
- This operation leads to various cache design issues which are discussed below:
### 4.B.i Cache Mapping Techniques
- Cache memory is very small as compared to main memory.
- and all blocks of main memory cannot be assigned to cache memory at once.
- so cache mapping techniques are required to assign particular block of main memory to the appropriate line in cache memory.
- there are basically three types of mapping techniques which are discussed below.
#### B.i.a Direct Mapping
- main memory block is assigned to a fixed cache line.
- the cache stores the content of main memory, the tag and valid bit
- here the memory address is divided into the tag, the index and offset.
- the index, which is defined by cache size, represents the cache address.
- index is used to select the particular the particular cache line.
- the tag from main memory address is compared to the tag stored in cache.
- in case the tag matches, the data from the cache line is accessed.
- however, a single cache line can store few blocks of main memory.
- so to select a particular block, the offset part of main memory address is used.
- the valid bit in cache is used to indicate the validity of data stored in the cache slot.
- figure:
	- ![[Pasted image 20260224163603.png | 600]]
- direct cache mapping is easy and simple in implementation.
- however, when two blocks of main memory which are assigned to a particular cache line are to be accessed frequently, then cache miss occurs repeateedly.
- this problem is commonly known as thrashing.
- also, replacement algorithm cannot be used, since the main memory blocks are mapped to a fixed cache line.
#### B.i.b Fully Associative mapping
- main memory block can be assigned to any slot of cache line.
- the main memory address is divided into tag field and offset field.
- the tag from main memory is compared to each tag in the cache line.
- After the tag matches the offset is used to select a particular word in cache line.
- Figure:
	- ![[Pasted image 20260224163851.png]]
- fully associative mapping provides high-flexibility as block of main memory can be assigned to any cache line.
- however, the comparison logic is required for each cache line which makes this mapping method complex and expensive to implement.
- Miss rate can increase if frequently required block is replaced, so appropriate replacement algorithm must be utilized for efficient cache implementation.
#### B.i.c Set Associative Mapping
- it is a compromise mapping which, somehow, follows both direct and fully associative mapping.
- the cache is divided into sets, each with number of cache lines
- a cache with a set of size N is called an N-way set associative cache.
- each block of main memory can be mapped to particular line of any sets (fixed line but varying sets) or any lines of particular set (fixed set but varying lines)
- take former case into consideration, the main memory address is divided into tag, index and offset.
- the index field is used to select the fixed cache line, and the tag field of main memory is compared to tag of each sets.
- when the particular set is selected, the offset is used to select the particular word from the set in which the tag matches.
- figure:
	- ![[Pasted image 20260224171607.png]]
- set associative cache mapping is more flexible and can reduce cache misses as compared to direct mapping.
- though the block of main memory is assigned to fixed cache line, block can be assigned to any sets of cache line.
- and proper implementation of cache replacement can be used to increase cache hit rate.
- also the comparison logic is not required for every cache line rather is required for only available sets which reduce the complexity and expense for implementing comparison logic.
### 4.B.ii Cache-Replacement Policy
- when cache is full and new main memory block is to be assigned to the cache then certain technique must be used to choose which cache line should be replaced.
- this mechanism of replacing the existing block by new set of blocks is referred as cache-replacement policy.
- in direct mapping, the main memory block always maps to the fixed cache line, so replacement is fixed. but fully associative and set associative can follow various replacement algorithms.
- Few algorithms:
	- Random replacement: replaces the block randomly without following any specific algorithm
	- LRU algorithm is based on time, in which block not accessed for longest time is replaced by the new block.
	- FIFO method uses queue mechanism to replace the first entered block.
		- each block is pushed into the queue when accessed.
		- and replacement is required when blocks are popped out from the queue.
	- LRU technique is based on number of time the block is accessed.
		- the block which accessed less number of times is replaced.
### 4.B.iii Cache Write Techniques
- Mechanism is required when content of cache is changed by the processor and the change must be updated to the corresponding main memory block.
- this technique of updating the main memory after change in cache is referred as cache write policy.
- there are two common cache write policy; write-through and write-back.
#### B.iii.a Write-through
- technique in which the main memory is updated immediately after the content in cache is changed.
- this technique is easier to implement but the processor has to wait for slower main memory access. 
- also there are chances of unnecessary writes resulting in substantial memory traffic
- for example, when a particular value is changed four times, the last updated value must only be updated in the main memory.
- but the memory is updated four times for every change causeing unncecessary memory access.
#### B.iii.b Write-back
- allows main memory to be updated only when cache line is to be replaced.
- extra bit is associated with each cache line to represent whether the content of cache line is changed or not
- based on the extra bit the corresponding main memory block is updated when cache line is about to be replaced
- extra bit and update checking increase system complexity
- it reduces number of slow main memory access and avoids memory congestion
### 4.B.iv Cache Impact on System Performance
- the performance of system is directly related to design and configuration of caches.
- total size of cache, degree of associativity and the data block size are important parameters that have direct impact on performance.
#### B.iv.a Cache size
- total number of bytes that the cache can store
- the tags and extra bits which do not contribute  to the size of the cache, are also stored in cache along with the data of main memory block.
- increasing the size of cache results in lower miss rates
- access of data from cache will be slower.
- so lrger cache size doesn't mean better performance strictly
#### B.iv.b Degree of associativity
- related to number of sets used in set associative cache implementation.
- increasing number of sets will improve hit rate
- however, additional logic requirement will increase the access time latency.
#### B.iv.c Cache Line size
- represents the size of each block in cache that holds the block of data of main memory.
- when line size is increased, the main memory access time is, obviously, reduced but only at the expense of more complex multiplexing circuitry which increases the access latency.
