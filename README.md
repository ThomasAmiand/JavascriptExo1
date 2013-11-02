JavascriptExo1
==============

Premier exercice du tp javascript

function adder(l,r){
        return function(v){

                return l(v) + r(v);
        }        

}

function mult(v){
        return function(e)
        {
                return v*e;
        }
}


//Les fonctions à implémenter

function sub(l){
        return function(v){

                return l - v;
        }        
}


//adder avec tableau d'arguments
function adder(){
        var resultat = 0;
        var table = Array.prototype.slice.call(arguments);
        
          return function(v){
                table.forEach(function(func){                                
                        resultat = resultat + func(v);
                });                        
                console.log(resultat);
                
        };
}



adder()(1); // 0
adder(mult(2))(1); // 2
adder(mult(2), mult(2), mult(2))(1); // 6
adder(mult(2), sub(2), mult(2))(1); // 5
