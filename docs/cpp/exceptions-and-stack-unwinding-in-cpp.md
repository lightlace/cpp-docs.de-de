---
title: Ausnahmen und Stapelentladung in C++
ms.date: 11/04/2016
ms.assetid: a1a57eae-5fc5-4c49-824f-3ce2eb8129ed
ms.openlocfilehash: 43d7945d53a0bd9993e75c04cceb3c8f5fec8ae2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569714"
---
# <a name="exceptions-and-stack-unwinding-in-c"></a>Ausnahmen und Stapelentladung in C++

Im C++-Ausnahmemechanismus geht die Steuerung von der throw-Anweisung zur ersten catch-Anweisung, die den ausgelösten Typ behandeln kann. Wenn die Catch-Anweisung erreicht wird, werden alle automatischen Variablen, die im Bereich zwischen der throw- und catch-Anweisungen in einem Prozess, der so genannten zerstört *stapelentladung*. Bei der Stapelentladung wird die Ausführung wie folgt fortgesetzt:

1. Erreicht der **versuchen** -Anweisung durch normale sequenzielle Ausführung. Der geschützte Bereich in der **versuchen** Block wird ausgeführt.

1. Wenn während der Ausführung des abgesicherten Abschnitts keine Ausnahme ausgelöst wird die **catch** Klauseln, die **versuchen** -Block nicht ausgeführt werden. Die Ausführung wird fortgeführt, bei der Anweisung nach dem letzten **catch** -Klausel, die das zugeordnete folgt **versuchen** Block.

1. Wenn eine Ausnahme, während der Ausführung des abgesicherten Abschnitts oder in einer Routine, die der abgesicherten Abschnitt entweder direkt oder indirekt aufruft ausgelöst wird, wird ein Ausnahmeobjekt erstellt, aus dem Objekt, das erstellt wird die **auslösen** Operanden. (Dies bedeutet, dass ein Kopierkonstruktor beteiligt sein kann.) An diesem Punkt sucht der Compiler eine **catch** -Klausel in einem höheren Ausführungskontext, der verarbeiten kann, eine Ausnahme des Typs, die ausgelöst wird, oder für eine **catch** Handler, der jeden Typ von Ausnahme verarbeiten kann. Die **catch** Handler werden überprüft, in der Reihenfolge ihrer Darstellung nach der **versuchen** Block. Wenn kein entsprechender Handler gefunden wird, wird der nächste dynamisch einschließende **versuchen** -Block ausgewertet wird. Dieser Prozess wird fortgesetzt, bis der äußerste einschließende **versuchen** -Block ausgewertet wird.

1. Wenn ein entsprechender Handler weiterhin nicht gefunden wird oder wenn während des Entladungsprozesses eine Ausnahme auftritt, bevor der Handler die Steuerung übernimmt, wird die vordefinierte Laufzeitfunktion `terminate` aufgerufen. Wenn eine Ausnahme auftritt, nachdem die Ausnahme ausgelöst wurde, aber bevor die Abwicklung beginnt, wird `terminate` aufgerufen.

1. Wenn kein übereinstimmendes **catch** Handler gefunden wird, und sie als Wert abfängt, die formale Parameter initialisiert, indem das Ausnahmeobjekt kopiert. Wenn er als Verweis abfängt, wird der Parameter so initialisiert, dass er auf das Ausnahmeobjekt verweist. Nachdem der formale Parameter initialisiert wurde, beginnt der Prozess der Stapelentladung. Dies beinhaltet die Löschung aller automatischen Objekte, die vollständig erstellt wurden – aber noch nicht zerstört, zwischen dem Beginn der der **versuchen Sie es** Block, der zugeordnet ist die **catch** Handler und die Auslösen der Ausnahme an. Beschädigung tritt in umgekehrter Reihenfolge der Konstruktion auf. Die **catch** Handler wird ausgeführt, und das Programm setzt die Ausführung nach dem letzten Handler fort. –, also auf der ersten Anweisung oder Konstrukt, das nicht ist eine **catch** Handler. Steuerelement kann nur eingeben einer **catch** Ereignishandler über eine ausgelöste Ausnahme, nie über eine **"GoTo"** Anweisung oder ein **Fall** -Bezeichnung in eine **wechseln** -Anweisung.

## <a name="stack-unwinding-example"></a>Beispiel für die Stapelentladung

Das folgende Beispiel zeigt, wie der Stapel entladen wird, wenn eine Ausnahme ausgelöst wird. Die Ausführung auf dem Thread springt von der throw-Anweisung in `C` auf die catch-Anweisung in `main` und entlädt währenddessen jede Funktionen. Beachten Sie die Reihenfolge, in der die `Dummy`-Objekte erstellt und dann zerstört werden, wenn sie den Gültigkeitsbereich verlassen. Beachten Sie außerdem, dass keine Funktion außer `main` abgeschlossen wird, die die catch-Anweisung enthält. Funktion `A` kehrt nie von ihrem Aufruf von `B()` zurück und `B` nie von seinem Aufruf von `C()`. Wenn Sie die Definition des `Dummy`-Zeigers und die zugehörige Löschanweisung auskommentieren und das Programm dann ausführen, sehen Sie, dass der Zeiger nie gelöscht wird. Dies zeigt, was geschehen kann, wenn Funktionen keine Ausnahmegarantie bieten. Weitere Informationen finden Sie unter "How to: Design for Exceptions". Wenn Sie die catch-Anweisung auskommentieren, können Sie nachvollziehen, was geschieht, wenn ein Programm aufgrund eines Ausnahmefehlers beendet wird.

```cpp
#include <string>
#include <iostream>
using namespace std;

class MyException{};
class Dummy
{
    public:
    Dummy(string s) : MyName(s) { PrintMsg("Created Dummy:"); }
    Dummy(const Dummy& other) : MyName(other.MyName){ PrintMsg("Copy created Dummy:"); }
    ~Dummy(){ PrintMsg("Destroyed Dummy:"); }
    void PrintMsg(string s) { cout << s  << MyName <<  endl; }
    string MyName; 
    int level;
};

void C(Dummy d, int i)
{ 
    cout << "Entering FunctionC" << endl;
    d.MyName = " C";
    throw MyException();   

    cout << "Exiting FunctionC" << endl;
}

void B(Dummy d, int i)
{
    cout << "Entering FunctionB" << endl;
    d.MyName = "B";
    C(d, i + 1);   
    cout << "Exiting FunctionB" << endl; 
}

void A(Dummy d, int i)
{ 
    cout << "Entering FunctionA" << endl;
    d.MyName = " A" ;
  //  Dummy* pd = new Dummy("new Dummy"); //Not exception safe!!!
    B(d, i + 1);
 //   delete pd; 
    cout << "Exiting FunctionA" << endl;   
}

int main()
{
    cout << "Entering main" << endl;
    try
    {
        Dummy d(" M");
        A(d,1);
    }
    catch (MyException& e)
    {
        cout << "Caught an exception of type: " << typeid(e).name() << endl;
    }

    cout << "Exiting main." << endl;
    char c;
    cin >> c;
}

/* Output:
    Entering main
    Created Dummy: M
    Copy created Dummy: M
    Entering FunctionA
    Copy created Dummy: A
    Entering FunctionB
    Copy created Dummy: B
    Entering FunctionC
    Destroyed Dummy: C
    Destroyed Dummy: B
    Destroyed Dummy: A
    Destroyed Dummy: M
    Caught an exception of type: class MyException
    Exiting main.

*/
```