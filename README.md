Em Python, **não existe polimorfismo de sobrecarga nativo** como em Java ou C#.  
Se você tentar criar duas funções com o mesmo nome na mesma classe, **a última sobrescreve a anterior**.  

Este repositório contém dois exemplos para explicar isso:

**Tentativa de sobrecarga que não funciona:**

<img width="398" height="339" alt="image" src="https://github.com/user-attachments/assets/ea765be5-1abc-4618-b5d6-96c3689e7cef" />


    c.falar()           # ERRO Faltando argumento 'tipo'
    c.falar("latido")   # Funciona


Explicação:  Python não guarda várias versões do mesmo método.
A segunda função falar(self, tipo) substituiu a primeira, tentar chamar falar() sem argumento resulta em erro.




### Arquivo : Arquivo: paliativo-para-funcionar-sobrecarga-fake ##

<img width="392" height="286" alt="image" src="https://github.com/user-attachments/assets/0105d24c-cb37-41d4-afca-95bae3d44be0" />


    c.falar()           # O animal faz um som
    c.falar("latido")   # O animal faz um som do tipo: latido



Explicação: 
Usando parâmetro opcional (tipo=None) conseguimos aceitar chamadas com ou sem argumento.
O método se comporta de forma diferente dependendo do argumento recebido.
Isso é chamado de “sobrecarga fake”, pois simula a sobrecarga de métodos de outras linguagens.


Então, Python não tem sobrecarga nativa, assim como Javascrit. Para aceitar diferentes números ou tipos de argumentos, usamos:
Parâmetros opcionais *args / **kwargs .A sobrescrita (override) funciona normalmente: a classe filha pode redefinir métodos da mãe.



### Referncias bibliográficas: ##

https://docs.python.org/3/tutorial/controlflow.html#defining-functions 
https://docs.python.org/pt-br/3/
https://peps.python.org/pep-0443/

