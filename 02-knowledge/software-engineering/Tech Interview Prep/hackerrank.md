---
tags:
  - area/knowledge
  - area/software-engineering
  - topic/testing
---


# HackerRank

1. **Counting Valleys**

function countingValleys(n, s) {
    let level = 0
    let valley = 0
    for(let i =0 ; i < n; i++) {
        if (s[i] == 'D') {
            if (level === 0) {
                valley++
            }
            level--
        } 
        if (s[i] == 'U') {
            level++
        }
    }
    return valley;
}

1. **Sock Merchant**

function sockMerchant(n, ar) {
    let matches = 0;
    let colour = {}
    for(let i = 0; i< n; i++) {
        if (colour[ar[i]]){
            matches++
            colour[ar[i]] = 0
        } else {
            colour[ar[i]] = 1
        }
    }
}

1. **Repeated String**

function repeatedString(s, n) {
	var inString = 0;
	var added = 0;
	for(var i = 0 ; i < s.length ; i++) {
		if(s[i] == 'a') {
			inString++;
			if(i < (n%s.length))
				added++;
		}
	}
	var repeats = (n- n%s.length)/s.length;
	return repeats*inString+added;
}

1. **E**
2. **E**
3. **E**

## Related
- [[software-engineering-moc]]
- [[switch-statement]]
- [[rxjx-reactive-programming]]
