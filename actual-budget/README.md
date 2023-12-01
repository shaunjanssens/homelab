# Actual Budget
 
Used for managing budgets. It's possible to import your bank transactions with GoCardless. 

- Website: https://actualbudget.com/
- Github: https://github.com/actualbudget/actual

## Application ports

- Web: 5006

## Notes

- On first start-up you will get a `Fatal Error - Actual requires access to SharedArrayBuffer in order to function properly`. This is because `https` is required for `SharedArrayBuffer`. You can ignore this error by clicking on "Advanced options" and checking the checkbox "I understand the risks...". 