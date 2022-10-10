# leetcode_database
All my leetcode problem solves
# 1393. Capital Gain/Loss

![image](https://user-images.githubusercontent.com/70795559/194944714-eb95a69e-23a9-4399-adb0-9480e8af2faa.png)
![image](https://user-images.githubusercontent.com/70795559/194944756-e4b3bb04-c6b0-48a8-993a-888a8ce85ee5.png)

# Solution 
select stock_name,
total_sell - total_buy as capital_gain_loss
from (
    select 
        stock_name,
        sum(case when operation = 'Sell' then price else 0 end) as total_sell,
        sum(case when operation = 'Buy' then price else 0 end) as total_buy
    from stocks
    group by stock_name) x 
    order by capital_gain_loss
