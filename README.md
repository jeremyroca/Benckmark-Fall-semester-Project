# Benckmark-Fall-semester-Project
This is the benchmark between Seal and Charms

For access to the benchmark just on Charms, you have to click on Benchmark_Project_FallSemester.xlsx.
When you are one the page of the repositories, you have to click on vew raw, for display and download the result.

For acces to the final benchamark, with all the different calculation tables on charm and seal, you have to click on Final_Benchmark.xlsx.
When you are one the page of the repositories, you have to click on vew raw, for display and download the result.

## Benchmark_Project_FallSemester.xlsx.
First global execution test on the solution implemented with charm crypto. 


## Final_Benchmark.xlsx.
### SEAL 10k
- param_poly_modulus_degree between 2^12 (4096) and 2^15 (32 768)
- param_number_random_values = 10 000 (corresponds to the number of users)
- param_range_random_values = 2 (range of the values that will be randomly selected)

In this case, we can observe that encryption is the major factor. Indeed more than 90% of the execution corresponds to the encryption step. From a value of 32 768 for the modulus polynomial, the sum takes time to be executed. Indeed the group is larger, the more ciphertexts to add are large which gives us a slower execution time.

All the rest of the steps during the execution of this solution are minimal and fast enough to execute


### SEAL 50k
- param_poly_modulus_degree between 2^12 (4096) and 2^14 (16 384)
- param_number_random_values = 50 000 (corresponds to the number of users)
- param_range_random_values = 2 (range of the values that will be randomly selected)

In this case, we can see as in the previous step that the encryption is the longest to execute, once again, the more the value of the modulus polynomial increases, the longer the sum takes to execute.

### SEAL 100k
- param_poly_modulus_degree between 2^12 (4096) and 2^13 (8192)
- param_number_random_values = 100 000 (corresponds to the number of users)
- param_range_random_values = 2 (range of the values that will be randomly selected)

For 100 000 users, my computer is not powerful enough to finish the program with value over 2^13. The processor uses more than 25 GB to encode and encrypt the messages. 
The execution time is based on the amount of encryption. The sum is more important in this case because we make a sum on 100,000 data which logically takes more time than for 10,000 users.

### Solution with Charm crypto and 10 000 users
- size of the group varies between 2^12 (4096) and 2^15(32 768)
- number of users = 10 000
- delta = 1 (range of values that will be randomly selected)

In this case, we can see that the encryption and the sum counts for 70% of the execution time. As the size of the group increases, the execution time of the secret key generation increases. We also notice that as the size of the group increases, the encryption does not increase and is executed in the 4 cases in about 5 seconds.
However, the generation of secret keys increases more and more to the point of exceeding the encryption execution time in the latter case


### Solution with Charm crypto and 50 000 users
- size of the group varies between 2^12 (4096) and 2^15(32 768)
- number of users = 50 000
- delta = 1 (range of values that will be randomly selected)

Compared to the previous case, we can see that the encryption and sum time remains the same even if the size of the group increases. The time is multiplied by 5 (logical because the number of users is increased by 5). From a certain group size, the key generation is slower than the encryption and sum.

### Solution with Charm crypto and 100 000 users
- size of the group varies between 2^12 (4096) and 2^15(32 768)
- number of users = 100 000
- delta = 1 (range of values that will be randomly selected)

For this last graph, we follow the previous law. the encryption and sum time is multiplied by 2 as the number of users. the execution time for the generation of private keys increases considerably and continues to increase as the size of the group increases. 

