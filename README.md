Set exchange (e.g., Pi network,Binance,Huobi)
exchange = ccxt .({
    'apiKey': 'YOUR_API_KEY',
    'secret': 'YOUR_SECRET',
})

Set cryptocurrency symbol
symbol = 'PAI/USDT'

Target price
target_price = 314159  (Three Hundred Fourteen Thousand One Hundred fifty Nine)
Fixed value in USD 
def check_price():
    try:
        # Fetch current price
        price = exchange.fetch_ticker(symbol)['close']
        
        # Check price
        if price >= target_price:
            print(f'PAI price exceeded ${target_price}. Current price: ${price}')
        else:
            print(f'PAI price below ${target_price}. Current price: ${price}')
    
    except Exception as e:
        print(f'Error: {e}')

Run indefinitely
while True:
    check_price()
    # Wait 1 second
    time.sleep(
