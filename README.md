# hodlminer binaries
Hodlminer binaries for Windows x64. Non AES-NI version is compiled by NiceHash. AVX version is build by Madzebra.

## hodlminer-avx2.exe (by Orava)
requires AES-NI and AVX2 support

## hodlminer-avx.exe (by Orava)
requires AES-NI and AVX support

## hodlminer-sse2.exe (by Orava)
requires AES-NI and SSE2 support (westmere architecture)

## hodlminer-core2-non_aes.exe (by NiceHash)
does not require AES-NI support

# Hodlminer 2018 v3
- NEW: Show block number, difficulty and stratum difficulty
       [2018-08-04 13:37:54] NEW BLOCK 488117, difficulty 0.004085, stratum difficulty 8.00
- NEW: New affinity parameter. --affinity=1 binds thread0 to cpu0, thread1 to cpu1 etc.
       --affinity=2 binds thread0 to cpu0, thread1 to cpu2, thread2 to cpu4, thread3 to cpu6 etc.
       This can be used to bind threads to only physical cores.

# Hodlminer 2018 v2
- NEW: Show colored text. Works in Windows 10.
- NEW: Show average hash rate in benchmark mode
- NEW: Show time average hash rate when mining. By default 10 last samples is used.This can be modified by --average=N parameter.
- NEW: Set CPU affinity by --affinity parameter. Thread0 is bound to CPU0, thread1 to CPU1 etc.
- NEW: Hodlminer tries to use large/huge page support if support is enabled in Windows. In order to use large page memory allocation
       there have to 1 GB of continous physical memory. Otherwise you get code 1450. The longer you run Windows the more fragmented
	   memory gets. In best cases I have got 1% increment in hash rate with large page support.  
- FIXED: Now Hodlminer gives more realistic hash rates readings https://github.com/Orava2/hodlminer/issues/1 .
       New hash rate readings are always lower than in version 2018 v1.
- FIXED: Old version caused segmentation fault when using thread counts 3, 6, 7, 19, 20, 21, 27, 30, 60, 63.
