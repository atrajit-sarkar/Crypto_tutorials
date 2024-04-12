# Preliminary
## Plain Text:
Plain text is a text that we need to encode with certain methods.
## Encoding function:
Encoding function is a map  $\epsilon:\mathcal{P} \rightarrow \mathcal{P}$
Where $\mathcal{P}$ is defined as $\mathcal{P}=\{A,B,C,D,....X,Y,Z,...\}$ as symbols desired. According to our [example](https://replit.com/@atrajitsarkar/Cryptographytutorial#.tutorial/01-Storing_data.md:4) we have, \
 $\mathcal{P}=\{A;B;C;D;....X;Y;Z;\text{ } ;",";".";?;0;1;2;3;4;5;6;7;8;9;!\}$ 
 
 ## Affine Cipher Encoding function:
 In case of affine cipher we have the following function of encoding:
 $\epsilon:\mathcal{P}\rightarrow \mathcal{P}$ defined by \
 $\mathcal{P}(p)=ap+b(mod |\mathcal{P}|) \text{ }\forall p\in \mathcal{P}$.
 