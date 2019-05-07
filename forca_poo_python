
# Hangman Game (Jogo da Forca)
# Programação Orientada a Objetos

# Import
import random
from join import join

# Board (tabuleiro)
board = ['''

>>>>>>>>>>Hangman<<<<<<<<<<

+---+
|   |
    |
    |
    |
    |
=========''', '''

+---+
|   |
O   |
    |
    |
    |
=========''', '''

+---+
|   |
O   |
|   |
    |
    |
=========''', '''

 +---+
 |   |
 O   |
/|   |
     |
     |
=========''', '''

 +---+
 |   |
 O   |
/|\  |
     |
     |
=========''', '''

 +---+
 |   |
 O   |
/|\  |
/    |
     |
=========''', '''

 +---+
 |   |
 O   |
/|\  |
/ \  |
     |
=========''']


# Classe
class Hangman:

    # Método Construtor
    def __init__(self, word):
        self.word=word
        self.stat = 0
        self.palavra = []

    # Método avança o vetor da forca
    def next(self):
        self.stat = self.stat+1

    # Método para printar o status do jogo
    def print_game_status(self):
        print(board[self.stat])
        str2 = ' '.join(map(str, self.palavra))
        print(str2)

    # Método para adivinhar a letra
    def guess(self, letter):
        i = 0
        p = self.word
        o = letter
        encontrados = []
        if (self.word.find(letter)== -1):
            self.next()
            return 0
        for letra in self.word:

            if letra == letter:
                #encontrados.append(i)
                self.palavra[i] = letter
            i += 1

    # Método para verificar se o jogo terminou
    def hangman_over(self):

        if self.stat == 7:
            return 6
        else:
            return 1

    # Método para verificar se o jogador venceu
    def hangman_won(self):
        str1 = ''.join(map(str,self.palavra))

        if str1.find('-')==-1:
            return 1
        else:
            return 0

    # Método para não mostrar a letra no board
    def hide_word(self):
        print(board[self.stat])
        for k in self.word:
            self.palavra.append('-')


# Função para ler uma palavra de forma aleatória do banco de palavras
#def rand_word():
 #   with open("palavras.txt", "rt") as f:
  #      bank = f.readlines()
   # return bank[0]

#Método pra facilitar e não ter que salvar o arquivo palavras
def rand_word():
    #digite a palavra aqui:
    bank = 'xablau'
    return bank

# Função Main - Execução do Programa
def main():
    # Objeto
    game = Hangman(rand_word())
    t = 0
    game.hide_word()
    while t==0:

        if game.hangman_over()==6:

            print("\n\nVocê perdeu")
            print('A palavra era ' + game.word)
            t=1
            break

        if game.hangman_won()==1:
            game.print_game_status()
            print('\nParabéns! Você venceu!!')
            print('A palavra era ' + game.word)
            break
        else:
            game.print_game_status()
            letter = input("digite uma letra: ")
            game.guess(letter)

    print('\nFoi bom jogar com você! Agora vá estudar!\n')




    # Enquanto o jogo não tiver terminado, print do status, solicita uma letra e faz a leitura do caracter

    # Verifica o status do jogo
    #game.print_game_status()

    # De acordo com o status, imprime mensagem na tela para o usuário



# Executa o programa
if __name__ == "__main__":
    main()
