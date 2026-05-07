
# Virtual Memory

The basic idea includes multiple memories, of different kids, sizes, speed. Typically DRAM and SSD. Small and fast main memory of DRAM, and big and slow disk memory.
These are combined to form one or more virtual address space.
Transparent to the user/programmer.

The running code and used data are stored in the main memory, the rest is put aside to external memory.
The memory space appears to be big to the code, bigger than the main memory. Even executables bigger than the main memory can be executed.

Only one part of the executable is running at a time, and as we progress, we override the previous memory.

Parts of programs and pieces of data are being moved between external and main memory - **swapping**.
The currently executed code and currently used data are in the main memory. The rest can be in the external memory.
The code works with logical addresses, not physical ones. Translation is done by the operating system - **paging**.

Possibility of unauthorized access protection. Problem induces **access privileges**.

Paging is the translation between logical and physical addresses.
The page table is always in the main memory.
Contains information on each logical page.
- If it is stored in the main memory, the page presence bit P is set.
- Where it is - the physical frame.
- Dirty bit D - has the bit been modified?
- If so, the page must be written back to the external memory.
- Possibly also other attribute bits.

Stored in the main memory.
Typical page size includes 512 B - 16 KB.
Typically small, many pages.

Could have this question in the third test.
We have the logical address.
We have the physical address.
The logical address is much wider, bigger address space, than physical we have available.
Then, we have the page table, and somewhere there is a pointer to the beginning of the page table. In the page table are these entries shown above.
Page number is the pointer to one entry of the page table. Pointer arithmetic. Begin + Index = Target.

The CPU (program) uses the logical (big) address space.
When accessing data (logical space address - the possibilities are:
a. The address is already mapped in the memory (flag P is set)
$\implies$ The logical address it translated to the physical one and the main memory operation (read/write) is performed.
b. The address is not mapped in the main memory, the data is in the external one.
$\implies$ Interrupt is invoked (**page miss**). If there are no free frames in the main memory, we need to free some. Typically, the **LRU** (Last Recently Used) strategy.
If the dirty bit is set for the released frame (i.e. the frame has been modified in the main memory), it is written to the external memory.

The respective frame is moved (copied) from the external memory to the main memory, then go to a.

Any physical frame can be moved to any logical frame.

The solution to the size problem of the page table is **two level paging**.
In very simple words, the logical address is now divided into three parts instead of two parts. The offset is the same as the frame number, the page number is almost the same, though now it depends on the directory.
We split the pages into directories. We have the pointers to these directories, and then access the individual pages by the page number offset.
Essentially, it's a table inside a table, making lookup/indices way more compact.

Though, this isn't enough! What we do is, we chain these, For 64-bit CPUs, we use **three-level paging**. We have a directory, a sub-directory, and then individual pages.

# Cache

// cache-misses! i remember this!

### Memory Hierarchy
The running application uses just a small part of memory in one period of time.
**Temporal Locality** - The application will most likely access data already accessed recently. Recently accessed data is stored in small and fast memory.
**Spatial locality** - The application will most likely access data near to the recently accessed data. Access data in larger blocks, store whole blocks.

Multiple memories.
Faster, smaller memories near the CPU.
Slower, bigger memories are further.

We have a cache per core, and a global cache that is shared by all cores.
// cores... mmhh.... wheatley...

The cache is a small and fast memory, implemented as SRAM.
Located between the main memory and CPU.
Associative memory - CAM (Content Addressable Memory)
The data is looked up by key, not address.

The principle is that the data is looked up by key, not address.
Directory instead of address decoder.
We have a key, going through the directory of keys.
Once we find a match, we move to the memory matrix which is table of the content (data) and the validity bit.
There is no pointer, this is realized in hardware.

The physical implementation is very fast, a bunch of DFFs in parallel.
XNOR are comparators. It is 1 when the inputs are equal.
All the bits stored in the flip flops must be matched with the data, and then we compare it with the validity bit too.

If we change the content at this address, and we won't write it into the cache, then we have to mention that it isn't valid. That is one of the scenarios that is possible with the validity bit.

This was the Fully Associative Cache.
It is very hardware consuming, which uses DFFs and XNORs, which is not really being used, as it is expensive.

M-way set associative cache differs.
Each record has only M possible locations for placing. The bigger the M, the better the associativity (efficiency).
The record is still looked up by key. 
The standard memory (SRAM) cells can be used for the directory.
Smaller, cheaper, trade-off between fully associative and standard SRAM.

What is the associativity of the fully associative cache? Full. As much as we have available entries.

Given the block of size $n$, we need $\log_2n$ to address its memory.

### Cache Applications
The caches are being used in Translation Look-aside Buffer (TLB) for speeding up the address translation in paging. 
They are used between the main memory and CPU, frequently and recently used data are temporarily stored in cache, transparent to the user.

Reading data from the main memory.
Reading cycle is initiated for both reading from the main memory and cache.
In case the data is found in cache, the main memory reading is terminated.
Otherwise, the data is read from the main memory then stored in cache.

### Reading Terms

**Cache Hit** - data found in cache.
**Hit Rate** - ratio of successfully found data. $\frac{cache~~hits}{memory~~requests}$
**Hit Time** - the time needed to find data in cache
**Cache Miss** - data not found in cache, must be read from the main memory
**Miss Rate** - the ratio of unsuccessfully found data = 1 − hit rate
**Miss Penalty** - the time to read from main memory.

### Writing
Dirty flag comes into play now.
First possibility, the data is not in the cache. Most common case, it is not written to the cache.
Otherwise, we do write to the memory and cache.
Sometimes we write only to the cache, and set the dirty bit.

Places to write data in cache.
Fully associative cache - anywhere
Direct mapped cache - only one possible place
M-way set associative cache - M possible places.

What if all places are occupied?
Last Recently Used (LRU). Best, but complex.
First-In First-Out (FIFO). Oldest records are replaced.
Least Frequently Used (LFU). Least frequently accessed record is replaced.



That's all about memories!