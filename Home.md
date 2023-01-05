# Bullish Product Wiki
A reference page containing the product specifications for Bullish API. View [Bullish API](https://api.exchange.bullish.com/docs/api/rest)
for technical specifications.

## Features
- Automated Market Making (AMM) Instructions

## Automated Market Making (AMM) Instructions

When a customer creates an AMM Instruction our AMM uses the instruction to place thousands of bids and offers into the orderbook. 
Those bids and offers generate income for the customer when other market participants trade against them. The bids and offers 
are also instantly adjusted and updated every time there is a trade. For more info on how AMM instructions generate income 
refer to https://support.bullish.com/hc/en-us/articles/4409724190617-Generating-income-with-Automated-Market-Making-Instructions
or reach out to your sales representative.

### What constitutes an AMM instruction
A customer creates an AMM Instruction by confirming their choice of market supported by Bullish, desired bid-offer spread 
from the set of provided options, specification of a price range across which the customer will make a market. 
Toggling on/off Bullish’s dynamic pricing function that adjusts their spreads based on market conditions and 
the amount of capital to be deployed (digital assets and/or fiat).

### Create AMM Instruction lifecycle
1. View available Fixed Spread Values
2. Select Spread Tier
3. Fetch Current AMM price
4. Set Price Boundaries
5. Determine amount of Assets to be deployed
6. Submit AMM instruction

#### View available Fixed Spread Values
- View available spread tiers from `Get Market by Symbol` endpoint and select desired fee tier corresponding to static spread and dynamic spread.

#### Select Spread Tier
- Each market has a list of fee tiers available. Each fee tier has a fixed spread and a dynamic spread parameter.
- If the dynamic spread is enabled, aims to increase your income by temporarily widening spreads when the market moves strongly.
- Select a fee tier based on your desired combination of static spread and dynamic spread parameters.

#### Fetch Current AMM price
- For the selected fee tier, fetch the current AMM price from `Get Tick by Symbol` endpoint.

#### Set Price Boundaries
- The price boundaries have lower and upper bound values which are entered in jumps of liquidity tick size associated with each market.
- An AMM instruction can be created as either one-sided (meaning only one asset of that market is deployed) or two-sided (meaning both assets of that market are deployed).
- Whether an AMM instruction is one-sided or two-sided is determined by the current AMM price associated for a market at that particular time of creating an AMM instruction.

#### Determine amount of Assets to be deployed
- For one-sided AMM instructions, only asset in a market is allocated .However for two-sided AMM instructions both assets have to be allocated in a particular ratio.
- The ratio is based upon the current AMM price, lower price bound and upper price bound. The ratio is calculated as follows:
````
p = square_root(current_amm_price)
l = square_root(price_lower_bound)
u = square_root(price_upper_bound)

ratio =  (p * u * (p - l)) / (u - p)
````
While creating a two-sided AMM instruction, you can decide on the amount of one asset you want to allocate and then derive the required amount of the other asset. 
A customer can decide on a base quantity and then calculate the required quote quantity.
````
base = 1.00000000
quote = base * ratio
````
Or decide on a quote quantity and then calculate the required base quantity.
````
quote = 5000.0000
base = quote / ratio
````
The combined USD value across both assets allocated must be at least 5,000 USD.

#### Submit AMM instruction
- See [creating an AMM instruction](https://github.com/bullish-exchange/api-examples/blob/master/create_amm_instruction.py) 
for a sample Python script
- See `Create AMM Instruction` endpoint for technical specifications.