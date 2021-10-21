<html>
<script>

var apikey = {
    key:'1257faea-cd1e-4b3f-b288-cf275f83e65e'
}
    
request('GET','https://pro-api.coinmarketcap.com/v1/global-metrics/quotes/latest?CMC_PRO_API_KEY=' + apikey.key)
.then((r1) => {
    var x1 = JSON.parse(r1.target.responseText);
    console.log(x1.data.quote.USD.total_market_cap);
}).catch(err => {
    console.log(err);
})  
    
function request(method, url) {
        return new Promise(function (resolve, reject) {
            var xhr = new XMLHttpRequest();
            xhr.open(method, url);
            xhr.onload = resolve;
            xhr.onerror = reject;
            xhr.send();
        });
}
</script>
</html>
