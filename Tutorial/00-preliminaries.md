# Preliminary
## Plain Text:
Plain text is a text that we need to encode with certain methods.
## Text Space:
$\mathcal{P}=\{A,B,C,D,....X,Y,Z,...\}$ is called text space. We can add mny more symbols and numbers and special characters to it. $|\mathcal{P}|$ is called the cardinality of the text space which is used as to do modulo operation in the following.
## Encoding function:
Encoding function is a map  $\epsilon:\mathcal{P} \rightarrow \mathcal{P}$
Where $\mathcal{P}$ is defined as $\mathcal{P}=\{A,B,C,D,....X,Y,Z,...\}$ as symbols desired. According to our [example](01-Storing_data.md#making-data-base) we have, \
 $\mathcal{P}=\\{A;B;C;D;....X;Y;Z;\text{ } ;",";".";?;0;1;2;3;4;5;6;7;8;9;!\\}$ 
 
 ## Affine Cipher Encoding function:
 In case of affine cipher we have the following function of encoding:
 $\epsilon:\mathcal{P}\rightarrow \mathcal{P}$ defined by \
 $\mathcal{P}(p)=ap+b(mod |\mathcal{P}|) \text{ }\forall p\in \mathcal{P}$.

 Now, to do mathematical operation like addition and multiplication as defined above we use the convension:

 ```python
 dict={0:'A',1:'B',2:'C' ,3:'D' ,4:'E' ,5:'F' ,6:'G' ,7:'H' ,8:'I' ,9:'J',10:'K',11:'L' ,12:'M' ,13:'N' ,14:'O' ,15:'P',16:'Q' ,17:'R' ,18:'S' ,19:'T' ,20:'U',21:'V' ,22:'W' ,23:'X' ,24:'Y' ,25:'Z',26:' ',27:',',28:'.',29:'?',30:'0',31:'1',32:'2',33:'3',34:'4',35:'5',36:'6',37:'7',38:'8',39:'9',40:'!'}
 ```

 ## Cipher Text:
 After encoding the plain text what we get is called is cipher text.
 
 ## Decoding Function:
 This is just the oppsoite of Encoding.
 In our [example](01-Storing_data.md#making-data-base)
$d:\mathcal{P}\rightarrow \mathcal{P}$ is defined as $d(c)=a^{-1}(c-b)(mod|\mathcal{P}|)$.

## Greatest Common Divisor(GCD):
Search for all the numbers that divides both a & b and find the max of all those numbers(d). The d is called the gcd of a & b. And dented by $d=gcd(a,b)$.

### Finding GCD of two numbers:
#### Euclidean Algorithm :
Simply divide a with b if $a\geq b$.\
$a=bq+r$, Where $0\leq r < b$.\
$b=rq_1+r_1$, Where $0\leq r_1 < r$.\
.\
.\
.\
.\
$r_n=r_{n+1}q_{n+2}+r_{n+2}$, Where $r_{n+2}=0$.\
and $r_{n+1}=gcd(a,b)$


## Inverse of a word:
First see the dictionary key (say a) of the word and invert it i.e. solve the equation $ax\equiv 1(mod|\mathcal{P}|)$.\
Inverse exits iff $gcd(a,|\mathcal{P}|)=1$.\

[next page](./01-Storing_data.md)

                            
