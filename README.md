# etoro-getSpread
get Etoro spread from the eToro watchlist 


#code js to run in the google chrome console 

1) Open the console of the Google chrome browser

instructions:
Open as panel
To open the dedicated Console panel, either:

Press Ctrl+Shift+J (Windows / Linux) or Cmd+Opt+J (Mac) or Right click mouse and Inspect.
Click on the console.


2) go to https://www.etoro.com/watchlists and copy and paste  the following code in the console:

for(var i = 1; i < 50; i++) { 

var name = $$("body > ui-layout > div > div > div.main-app-view.ng-scope > watchlist-watchlist > div.main-content.list-view.ng-scope > watchlist-list > div > div.table-body.market.ng-pristine.ng-untouched.ng-valid.ng-scope.ui-sortable.ui-sortable-disabled.ng-not-empty > div:nth-child("+ i +") > watchlist-item > div > div.table-name-cell.table-cell.pointer.ui-sortable-handle > div.user-info > span.user-nickname.ng-binding")[0].innerText;

var sell = $$("body > ui-layout > div > div > div.main-app-view.ng-scope > watchlist-watchlist > div.main-content.list-view.ng-scope > watchlist-list > div > div.table-body.market.ng-pristine.ng-untouched.ng-valid.ng-scope.ui-sortable.ui-sortable-disabled.ng-not-empty > div:nth-child("+ i +") > watchlist-item > div > div.table-info > div.table-cell.mid-cell.etoro-horizontal.etoro-float-clear > div.etoro-sell-button.ng-scope > div > div.etoro-price-value > span")[0].innerText;

var buy = $$("body > ui-layout > div > div > div.main-app-view.ng-scope > watchlist-watchlist > div.main-content.list-view.ng-scope > watchlist-list > div > div.table-body.market.ng-pristine.ng-untouched.ng-valid.ng-scope.ui-sortable.ui-sortable-disabled.ng-not-empty > div:nth-child("+ i +") > watchlist-item > div > div.table-info > div.table-cell.mid-cell.etoro-horizontal.etoro-float-clear > div.etoro-buy-button.ng-scope > div > div.etoro-price-value > span")[0].innerText;

sell = new Number(sell);

buy = new Number(buy);

var percentage = ((buy-sell)/sell)*100;

percentage = parseFloat(percentage).toFixed(2);

console.log("name: "+name+"  percentage: "+percentage+"  sell: "+sell+"   buy: "+buy);   

$$("body > ui-layout > div > div > div.main-app-view.ng-scope > watchlist-watchlist > div.main-content.list-view.ng-scope > watchlist-list > div > div.table-body.market.ng-pristine.ng-untouched.ng-valid.ng-scope.ui-sortable.ui-sortable-disabled.ng-not-empty > div:nth-child("+ i +") > watchlist-item > div > div.table-name-cell.table-cell.pointer.ui-sortable-handle > div.user-info > span.user-nickname.ng-binding")[0].innerText = name +"%" + percentage;	


### Author: Giuseppe Filomena
#### email: salsx@hotmail.it
#### etoroID: salsx88
