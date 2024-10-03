import datetime
import time
#parte1 e parte2
#Descrever a utilização das estruturas de condição if e else em Python
#Descrever a utilização da estrutura de condição else if (elif) em Python
#utilizarei as horas
horas_agora = datetime.datetime.now()
horas = int(horas_agora.hour)
#if e utilizado para verificar se uma condição é verdadeira e executa-la em caso afirmativo.
if horas >= 6 and horas <= 12:
    print("Bom dia")
#elif permite verificar várias condições após a verificação do if.
# se caso o if for falso, o codigo seguinte elif sera verificado, se o mesmo for verdadeiro, sera executado.
elif horas >= 12 and horas <= 18:
    print("Boa tarde")
elif horas >= 18 and horas <= 24:
    print("Boa noite")
#else é executado caso if ou elif não sejam verdadeiros.
else:
    print("Já está tarde, seria bom ir dormir")
print(horas_agora.hour,":", horas_agora.minute,":", horas_agora.second)
#parte3
#Descrever a utilização da estrutura de repetição while em Python
poltronas = 0
passageiros = 0
#o while permite que o bloco seja repetido diversas vezes, caso a condição seja verdadeira.
while poltronas < 36:
    passageiros = int(input("Quantos passageiros embarcaram ? "))
    poltronas = poltronas + passageiros
else:
    print("Espaço limite atingido, por favor espere o próximo ônibus.")
#parte4
#Descrever a utilização da estrutura de repetição for em Python
#for é utilizado para repetir determinadas vezes o códigos dentro de um parametro.
for i in range(0,passageiros):
    print(i)
else:
    print(passageiros)
    print("Ultimos passageiros")
#parte5
#Descrever a utilização de funções em Python
valor_da_passagem = 22.5
print("Preço da passagem: ",valor_da_passagem)
#def é uma função que cria blocos para fins específicos, que podem ser utilizado varias vezes em um código.
def inposto(valor_da_passagem):
    return valor_da_passagem * 0.7
total = valor_da_passagem + inposto(valor_da_passagem)
print(inposto(valor_da_passagem), "inposto")
print("valor total:", total)
#parte6
#Descrever a utilização argumentos de funções no Python
loginUsuario = input("Quem está acessando essa maquina? ")
if loginUsuario.lower() == "admin":
    print("Seja bem vido ADM!")
else:
    print("Seja bem vido usuario!")
#Fiz uma cauculadora usando o tkinter.
from tkinter import *
from tkinter import ttk

cor1 = "#1b1c1b" #cinza escuro
cor2 = "#233954" #azul escuro
cor3 = "#3a82c2" #azul claro
cor4 = "#c95414" #laranja
cor5 = "#f53838" #vermelho
cor6 = "#fcf7f7" #branco
cor7 = "#80b7e8" #teclado azul bem claro
#app
janela =Tk()
janela.title('CAUCULADORA')
janela.geometry("235x270")
#tela 1 e tela 2
janela.config(bg=cor1)
frame_tela = Frame(janela, width=235, height=70, bg=cor2)
frame_tela.grid(row=0, column=0)
frame_teclado = Frame(janela, width=235, height=250)
frame_teclado.grid(row=1, column=0)
#armazena dados
num_digitados = ''
#visor
valor_teclas = StringVar()
#chamando a função
def entrada_val(event):
    global num_digitados
    num_digitados = num_digitados + str(event)
    valor_teclas.set(num_digitados)
#cauculando
def caucular():
    global num_digitados
    resultado = eval(num_digitados)
    valor_teclas.set(str(resultado))
#limpar tela
def limpar_tela():
    global num_digitados
    num_digitados = ""
    valor_teclas.set("")
#escrito
lab = Label(frame_tela, textvariable = valor_teclas, width=20, height=2, font="Sans 20 bold", bg=cor2, fg=cor6)
lab.place(x=-50, y=15)
#teclas
tec7 = Button(frame_teclado, command= lambda: entrada_val('7'), text="7", width=6, height=2, font="Sans 9 bold", relief=RAISED, overrelief=RIDGE)
tec7.place(x=0, y=0)
tec8 = Button(frame_teclado, command= lambda: entrada_val('8'), text="8", width=6, height=2, font="Sans 9 bold", relief=RAISED, overrelief=RIDGE)
tec8.place(x=50, y=0)
tec9 = Button(frame_teclado, command= lambda: entrada_val('9'), text="9", width=6, height=2, font="Sans 9 bold", relief=RAISED, overrelief=RIDGE)
tec9.place(x=100, y=0)
tec4 = Button(frame_teclado, command= lambda: entrada_val('4'), text="4", width=6, height=2, font="Sans 9 bold", relief=RAISED, overrelief=RIDGE)
tec4.place(x=0, y=40)
tec5 = Button(frame_teclado, command= lambda: entrada_val('5'), text="5", width=6, height=2, font="Sans 9 bold", relief=RAISED, overrelief=RIDGE)
tec5.place(x=50, y=40)
tec6 = Button(frame_teclado, command= lambda: entrada_val('6'), text="6", width=6, height=2, font="Sans 9 bold", relief=RAISED, overrelief=RIDGE)
tec6.place(x=100, y=40)
tec1 = Button(frame_teclado, command= lambda: entrada_val('1'), text="1", width=6, height=2, font="Sans 9 bold", relief=RAISED, overrelief=RIDGE)
tec1.place(x=0, y=80)
tec2 = Button(frame_teclado, command= lambda: entrada_val('2'), text="2", width=6, height=2, font="Sans 9 bold", relief=RAISED, overrelief=RIDGE)
tec2.place(x=50, y=80)
tec3 = Button(frame_teclado, command= lambda: entrada_val('3'), text="3", width=6, height=2, font="Sans 9 bold", relief=RAISED, overrelief=RIDGE)
tec3.place(x=100, y=80)
tec10 = Button(frame_teclado, command= lambda: entrada_val('.'), text=".", width=6, height=2, font="Sans 9 bold", relief=RAISED, overrelief=RIDGE)
tec10.place(x=0, y=120)
tec11 = Button(frame_teclado, command= lambda: entrada_val('0'), text="0", width=13, height=2, font="Sans 9 bold", relief=RAISED, overrelief=RIDGE)
tec11.place(x=50, y=120)
#tec limpar
tec_limp = Button(frame_teclado, command= limpar_tela, text="C", width=11, height=2, bg=cor5, fg=cor6, font="Sans 9 bold", relief=RAISED, overrelief=RIDGE)
tec_limp.place(x=150, y=0)
#funções
adi = Button(frame_teclado, command= lambda: entrada_val('+'), text="+", width=11, height=2, bg=cor3, fg=cor6, font="Sans 9 bold", relief=RAISED, overrelief=RIDGE)
adi.place(x=150, y=40)
sub = Button(frame_teclado, command= lambda: entrada_val('-'), text="-", width=11, height=2, bg=cor3, fg=cor6, font="Sans 9 bold", relief=RAISED, overrelief=RIDGE)
sub.place(x=150, y=80)
mult = Button(frame_teclado, command= lambda: entrada_val('*'), text="x", width=11, height=2, bg=cor3, fg=cor6, font="Sans 9 bold", relief=RAISED, overrelief=RIDGE)
mult.place(x=150, y=120)
div = Button(frame_teclado, command= lambda: entrada_val('/ '), text="/", width=11, height=2, bg=cor3, fg=cor6, font="Sans 9 bold", relief=RAISED, overrelief=RIDGE)
div.place(x=150, y=160)
#resultado
resul = Button(frame_teclado, command= caucular, text="=", width=21, height=2, bg=cor2, fg=cor6, font="Sans 9 bold", relief=RAISED, overrelief=RIDGE)
resul.place(x=-5, y=160)
janela.mainloop()
