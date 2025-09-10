Em Python, **não existe polimorfismo de sobrecarga nativo** como em Java ou C#.  
Se você tentar criar duas funções com o mesmo nome na mesma classe, **a última sobrescreve a anterior**.  

Este repositório contém dois exemplos para explicar isso:

**Tentativa de sobrecarga que não funciona:**

class Animal:
    # Tentativa de criar duas versões do método
    def falar(self):
        print("O animal faz um som")
    # Esta sobrescreve a anterior
    def falar(self, tipo):
        print(f"O animal faz um som do tipo: {tipo}")

class Cachorro(Animal):
    pass

if __name__ == "__main__":
    c = Cachorro()
    c.falar()           # ERRO Faltando argumento 'tipo'
    c.falar("latido")   # Funciona


Explicação:  Python não guarda várias versões do mesmo método.
A segunda função falar(self, tipo) substituiu a primeira, tentar chamar falar() sem argumento resulta em erro.




### Arquivo : Arquivo: paliativo-para-funcionar-sobrecarga-fake ##

class Animal:
    def falar(self, tipo=None):
        if tipo:
            print(f"O animal faz um som do tipo: {tipo}")
        else:
            print("O animal faz um som")

class Cachorro(Animal):
    pass

if __name__ == "__main__":
    c = Cachorro()
    c.falar()           # O animal faz um som
    c.falar("latido")   # O animal faz um som do tipo: latido



Explicação: 
Usando parâmetro opcional (tipo=None) conseguimos aceitar chamadas com ou sem argumento.
O método se comporta de forma diferente dependendo do argumento recebido.
Isso é chamado de “sobrecarga fake”, pois simula a sobrecarga de métodos de outras linguagens.


Então, Python não tem sobrecarga nativa, assim como Javascrit. Para aceitar diferentes números ou tipos de argumentos, usamos:
Parâmetros opcionais *args / **kwargs .A sobrescrita (override) funciona normalmente: a classe filha pode redefinir métodos da mãe.



### Referncias bibliográficas: ##

https://docs.python.org/3/tutorial/controlflow.html#defining-functions e https://peps.python.org/pep-0443/


Tentar chamar falar() sem argumento resulta em erro.
