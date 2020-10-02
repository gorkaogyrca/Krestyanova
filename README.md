# Krestyanova
let parasits = [
{title: "кек", count:8},
{title: "ну", count:75},
{title: "блин", count:14},
{title: "это", count:123},
{title: "лол", count:54},
{title: "короче", count:198},
];
console.log("Список известных слов паразитов");
console.log(Object.values(parasits));
let promise = new Promise(function(resolve, reject){
  setTimeout(() => {  
  let max;
  for(let i = 0; i<parasits.length; i++){
    for(let j = i+1; j<parasits.length; j++){
      if (parasits[i].count < parasits[j].count){
        max = parasits[j];
        parasits[j]= parasits[i];
        parasits[i] = max;
      }
    }
}
  resolve((Object.values(parasits)));
  },3000);
})
promise.then(()=>{
  console.log(Object.values(parasits));
})
