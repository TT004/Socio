# Socio
Crie um programa que receba três nomes de sócios e a porcentagem que cada um possui da empresa, em seguida receba o valor total da empresa e calcule o valor correspondente de cada sócio.
from dataclasses import dataclass

@dataclass
class Socio:
    nome: str
    porcentagem: float

def ler_socio():
    nome = input('Digite o nome do socio: ')
    porcentagem = float(input('Digite a % do socio: '))
    socio = Socio(nome, porcentagem)
    return socio

def calcular_parte(socio: Socio, total: float ) -> float:
    return socio.porcentagem / 100 * total


def print_socio(socio: Socio, total: float):
    parte = calcular_parte(socio, total)
    print(f'O socio {socio.nome} tem R${parte:.2f}')



valor_empresa = float(input('Digite o valor da empresa: '))


socio_1 = ler_socio()
socio_2 = ler_socio()
socio_3 = ler_socio()
print_socio(socio_1, valor_empresa)
print_socio(socio_2, valor_empresa)
print_socio(socio_3, valor_empresa)
