---
title: Ausnahmen und Stapelentladung in C++ | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
ms.assetid: a1a57eae-5fc5-4c49-824f-3ce2eb8129ed
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: eedfb9c453fbd48ef2c5868fb186156397eeb500
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="exceptions-and-stack-unwinding-in-c"></a>Ausnahmen und Stapelentladung in C++
Im C++-Ausnahmemechanismus geht die Steuerung von der throw-Anweisung zur ersten catch-Anweisung, die den ausgelösten Typ behandeln kann. Wenn die Catch-Anweisung erreicht wird, werden alle automatischen Variablen, die im Bereich zwischen der throw- und catch-Anweisungen in einem Prozess, der sogenannten zerstört *stapelentladung*. Bei der Stapelentladung wird die Ausführung wie folgt fortgesetzt:  
  
1.  Die Steuerung erreicht die `try`-Anweisung durch normale sequenzielle Ausführung. Der geschützte Bereich im Block `try` wird ausgeführt.  
  
2.  Wenn während der Ausführung des abgesicherten Abschnitts keine Ausnahme ausgelöst wird, werden die `catch`-Klauseln, die dem `try`-Block folgen, nicht ausgeführt. Die Ausführung wird mit der Anweisung nach der letzten `catch`-Klausel fortgesetzt, die auf den zugeordneten `try`-Block folgt.  
  
3.  Wird eine Ausnahme während der Ausführung des abgesicherten Abschnitts oder in einer Routine, die aus dem abgesicherten Abschnitt entweder direkt oder indirekt aufgerufen wird, ausgelöst, wird ein Ausnahmeobjekt von dem Objekt erstellt, das durch den `throw`-Operanden erstellt wurde. (Dies bedeutet, dass ein Kopierkonstruktor beteiligt sein kann.) An diesem Punkt sucht der Compiler nach einer `catch`-Klausel in einem höheren Ausführungskontext, die eine Ausnahme des ausgelösten Typs behandeln kann, oder einen `catch`-Handler, der jeden Ausnahmetyp behandeln kann. Die `catch`-Handler werden in der Reihenfolge ihrer Darstellung nach dem `try`-Block überprüft. Wenn kein entsprechender Handler gefunden wird, wird der nächste dynamisch einschließende `try`-Block untersucht. Dieser Prozess wird fortgesetzt, bis der äußerste einschließende `try`-Block ausgewertet wird.  
  
4.  Wenn ein entsprechender Handler weiterhin nicht gefunden wird oder wenn während des Entladungsprozesses eine Ausnahme auftritt, bevor der Handler die Steuerung übernimmt, wird die vordefinierte Laufzeitfunktion `terminate` aufgerufen. Wenn eine Ausnahme auftritt, nachdem die Ausnahme ausgelöst wurde, aber bevor die Abwicklung beginnt, wird `terminate` aufgerufen.  
  
5.  Wenn ein entsprechender `catch`-Handler gefunden wird und Variablen als Wert abfängt, wird sein formaler Parameter initialisiert, indem das Ausnahmeobjekt kopiert wird. Wenn er als Verweis abfängt, wird der Parameter so initialisiert, dass er auf das Ausnahmeobjekt verweist. Nachdem der formale Parameter initialisiert wurde, beginnt der Prozess der Stapelentladung. Dies beinhaltet die Löschung aller automatischen Objekte, die zwischen dem Anfang des `try`-Blocks des `catch`-Handlers und der Auslöseseite der Ausnahme vollständig erstellt (jedoch noch nicht gelöscht) wurden. Beschädigung tritt in umgekehrter Reihenfolge der Konstruktion auf. Der `catch`-Handler wird ausgeführt und das Programm setzt die Ausführung nach dem letzten Handler fort (das heißt, bei der ersten Anweisung oder dem ersten Konstrukt, das kein `catch`-Handler ist). Die Steuerung kann einem `catch`-Handler nur durch eine ausgelöste Ausnahme beitreten, nie über eine `goto`-Anweisung oder eine `case`-Bezeichnung in einer `switch`-Anweisung.  
  
## <a name="stack-unwinding-example"></a>Beispiel für die Stapelentladung  
 Das folgende Beispiel zeigt, wie der Stapel entladen wird, wenn eine Ausnahme ausgelöst wird. Die Ausführung auf dem Thread springt von der throw-Anweisung in `C` auf die catch-Anweisung in `main` und entlädt währenddessen jede Funktionen. Beachten Sie die Reihenfolge, in der die `Dummy`-Objekte erstellt und dann beschädigt werden, wenn sie den Gültigkeitsbereich verlassen. Beachten Sie außerdem, dass keine Funktion außer `main` abgeschlossen wird, die die catch-Anweisung enthält. Funktion `A` kehrt nie von ihrem Aufruf von `B()` zurück und `B` nie von seinem Aufruf von `C()`. Wenn Sie die Definition des `Dummy`-Zeigers und die zugehörige Löschanweisung auskommentieren und das Programm dann ausführen, sehen Sie, dass der Zeiger nie gelöscht wird. Dies zeigt, was geschehen kann, wenn Funktionen keine Ausnahmegarantie bieten. Weitere Informationen finden Sie unter "How to: Design for Exceptions". Wenn Sie die catch-Anweisung auskommentieren, können Sie nachvollziehen, was geschieht, wenn ein Programm aufgrund eines Ausnahmefehlers beendet wird.  
  
```  
#include <string>  
#include <iostream>  
using namespace std;  
  
class MyException{};  
class Dummy  
{  
    public:  
    Dummy(string s) : MyName(s) { PrintMsg("Created Dummy:"); }  
    Dummy(const Dummy& other) : MyName(other.MyName){ PrintMsg("Copy created Dummy:"); }  
    ~Dummy(){ PrintMsg("Destroyed Dummy:"); }  
    void PrintMsg(string s) { cout << s  << MyName <<  endl; }  
    string MyName;   
    int level;  
};  
  
void C(Dummy d, int i)  
{   
    cout << "Entering FunctionC" << endl;  
    d.MyName = " C";  
    throw MyException();     
  
    cout << "Exiting FunctionC" << endl;  
}  
  
void B(Dummy d, int i)  
{  
    cout << "Entering FunctionB" << endl;  
    d.MyName = "B";  
    C(d, i + 1);     
    cout << "Exiting FunctionB" << endl;   
}  
  
void A(Dummy d, int i)  
{   
    cout << "Entering FunctionA" << endl;  
    d.MyName = " A" ;  
  //  Dummy* pd = new Dummy("new Dummy"); //Not exception safe!!!  
    B(d, i + 1);  
 //   delete pd;   
    cout << "Exiting FunctionA" << endl;     
}  
  
int main()  
{  
    cout << "Entering main" << endl;  
    try  
    {  
        Dummy d(" M");  
        A(d,1);  
    }  
    catch (MyException& e)  
    {  
        cout << "Caught an exception of type: " << typeid(e).name() << endl;  
    }  
  
    cout << "Exiting main." << endl;  
    char c;  
    cin >> c;  
}  
  
/* Output:  
    Entering main  
    Created Dummy: M  
    Copy created Dummy: M  
    Entering FunctionA  
    Copy created Dummy: A  
    Entering FunctionB  
    Copy created Dummy: B  
    Entering FunctionC  
    Destroyed Dummy: C  
    Destroyed Dummy: B  
    Destroyed Dummy: A  
    Destroyed Dummy: M  
    Caught an exception of type: class MyException  
    Exiting main.  
  
*/  
  
```