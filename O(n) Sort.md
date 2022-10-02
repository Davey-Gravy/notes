```c
int counts[100] = {0};
for (i=0; i<n; i++) {
	counts[arr[i]] += 1;
}
for (i=0; i<sizeof(counts); i++) {
	print(i*counts[i])
}
```