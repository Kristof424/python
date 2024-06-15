Data:

class Nev:
    def __init__(self,sor:str) -> None:
        adatok=sor.split(';')
        self.valami=adatok[0]

Functions:

from data import Nev

nevek:list[Nev]=[]

def beolvas(fajlnev:str):
    f=open(fajlnev,'r',encoding='utf8')
    f.readline()
    for sor in f:
        nevek.append(Nev(sor.strip()))
    f.close()

def keresofuggveny()->Nev:
    legdragabb=nevek[0]
    for nev in nevek[1:]:
        if nev.valami>legdragabb.valami:
            legdragabb=nev
    return legdragabb # ez egy osztálypéldány minden adatával

Main:
legdragabb=keresofuggveny()
