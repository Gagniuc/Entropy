# Entropy of text

This application calculates the entropy of text. Entropy is a measure of the uncertainty in a random variable. In the context of information theory the term "Entropy" refers to the Shannon entropy:

<img src="https://github.com/Gagniuc/Entropy-of-strings/blob/main/img/entropy%20eq.png?raw=true" height="90" alt="Entropy">

Which can also be written as:

<img src="https://github.com/Gagniuc/Entropy-of-strings/blob/main/img/entropy.png?raw=true" height="100" alt="Entropy">

Where <i>n</i> represents the total number of symbols in the alphabet of a sequence and <i>p<sub>i<sub></i> represents the probability of occurrence of a symbol <i>i</i> found in the alphabet. For more detailed information on entropy please see the specialized chapter from the book entitled <i>Algorithms in Bioinformatics: Theory and Implementation</i>.
	
```js

function entropy(c){

	//ALPHABET DETECTION
	var a = [];
	var t = c.split('');
	var k = t.length;

	for(var i=0; i<=k; i++){
		var q = 1;
		for(var j=0; j<=a.length; j++){
			if (t[i] === a[j]) {q = 0;}
		}
		if (q === 1) {a.push(t[i]);}
	}

	var e = 0;
	var r = '';
	var l = '';

	for(var i=0; i<=a.length-1; i++){
				
		r = c.replace(new RegExp(a[i], 'g'),'').length;
					
		l = a[i];
		a[i]=(k-r)/k;

		//e += -(a[i]*Log(2,a[i]));
		e += (a[i]*Log(2,(1/a[i])));
	}

	return e;
}

function Log(n, v) {
	return Math.log(v) / Math.log(n);
}
```

Live demo: https://gagniuc.github.io/Entropy-of-Text/

![screenshot](https://github.com/Gagniuc/Entropy/blob/main/Entropy.png)


# References

<i>Paul A. Gagniuc. Algorithms in Bioinformatics: Theory and Implementation. John Wiley & Sons, Hoboken, NJ, USA, 2021, ISBN: 9781119697961.</i>
