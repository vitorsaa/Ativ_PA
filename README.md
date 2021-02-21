# Ativ_PA
Atividade de Programação Aplicada

from random import randint
from time import sleep

jogadores = {input(f'\nNome do jogador {i}: ').capitalize(): randint(1, 6) for i in range(1, 5)}

for k, v in jogadores.items():
   sleep(1), print(f'\n{k} tirou {v}.'), sleep(1)

ranking = sorted(jogadores.items(), key=lambda item: item[1], reverse=True)

print(), print('-' * 32)
print(f'| {"Ranking dos jogadores":^28} |')
print('-' * 32)
print(f'| Posição |  Jogador  | Pontos |')
print('-' * 32)
posicao = 1
for num in range(len(ranking)):
   if num == 0 or ranking[num][1] == ranking[num - 1][1]:
       print(f'| {str(posicao) + "º":^7} | {ranking[num][0]:^9} | {ranking[num][1]:^6} |')
   else:
       posicao += 1
       print(f'| {str(posicao) + "º":^7} | {ranking[num][0]:^9} | {ranking[num][1]:^6} |')
print('-' * 32)

