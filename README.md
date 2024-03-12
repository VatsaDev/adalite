# Adalite
Using the Adalite optimizer on nanogpt, like Lilith, but with less mem usage



## Running tests

 - Test 4, going lower, lr 8e-5, 

 - Test 3, wait what? a lower lr of 1e-4 keeps loss at a stable drop, and val loss is better than adam by about ~0.2?

 ![Screen Shot 2024-03-12 at 12 18 30 AM](https://github.com/VatsaDev/adalite/assets/71975550/32d5f9a3-5bbe-4ece-b21e-0c4e9617a344)

 - Test 2, using a higher lr happens to not work at all, (was trying 1e-3/8e-4/5e-4, but that also goes Nan in 400/800/2000 steps), there are strange lr issues in this optimizer

 - Test 1, with adalite at all the defaults except lr at 3e-4, was using the nanogpt default of 1e-2, but it went to Nan in like 100 steps, here the adamW baseline is the default karpathy shakespeare-GPT, both at 10m parameters, tiny-shakespeare dataset. These two appear to take the same average time, 100ms per step for 16k tokens. Adam here is clearly superior, will have to see if my hyper-params are bad, or scheduler, or if batch-size helps

![Screen Shot 2024-03-11 at 10 33 02 PM](https://github.com/VatsaDev/adalite/assets/71975550/1b4cf829-6979-45f1-a717-84c25ecbfab7)


