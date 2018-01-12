---
title: Bereich (Visual C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- classes [C++], scope
- scope [C++]
- function prototypes [C++], scope
- class scope
- prototype scope
- functions [C++], scope
- scope, C++ names
ms.assetid: 81fecbb0-338b-4325-8332-49f33e716352
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 55baa4496522336a5a64ee81daa7a8ce484534c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="scope-visual-c"></a>Bereich (Visual C++)
C++-Namen können nur in bestimmten Bereichen eines Programms verwendet werden. Dieser Bereich wird als Gültigkeitsbereich des Namens bezeichnet. Der Gültigkeitsbereich bestimmt die Lebensdauer eines Namens, der kein statisches Objekt angibt. Der Gültigkeitsbereich bestimmt außerdem die Sichtbarkeit eines Namens, wenn Klassenkonstruktoren und -destruktoren aufgerufen werden, und wenn lokale Gültigkeitsbereichsvariablen initialisiert werden. (Weitere Informationen finden Sie unter [Konstruktoren](../cpp/constructors-cpp.md) und [Destruktoren](../cpp/destructors-cpp.md).) Es gibt fünf Arten von Gültigkeitsbereichen:  
  
-   **Lokalen Gültigkeitsbereich** ein Name, der innerhalb eines Blocks deklariert ist nur innerhalb dieses Blocks und-Blöcke eingeschlossen werden, damit und erst nach dem Zeitpunkt der Deklaration zugegriffen werden kann. Die Namen von formalen Argumenten für eine Funktion im Gültigkeitsbereich des äußersten Funktionsblocks haben lokale Gültigkeit, so als ob sie direkt im Block deklariert wurden, der den Funktionstext einschließt. Betrachten Sie das folgende Codefragment:  
  
    ```  
    {  
        int i;  
    }  
    ```  
  
     Da die Deklaration von `i` in einem Block ist, der von geschweiften Klammern eingeschlossen wird, hat `i` lokale Gültigkeit und ist nie zugänglich, weil kein Code vor der schließenden Klammer darauf zugreift.  
  
-   **Funktionsgültigkeitsbereich** Bezeichnungen sind die einzigen Namen, die Funktionsgültigkeitsbereich haben. Sie können überall innerhalb einer Funktion verwendet werden. Außerhalb der Funktion kann aber nicht auf sie zugegriffen werden. Formale Argumente (Argumente, die in den Funktionsdefinitionen angegeben sind) auf Funktionen gelten als im Gültigkeitsbereich des äußersten Blocks des Funktionstexts.  
  
-   **Dateigültigkeitsbereichs** einen beliebigen Namen, die außerhalb aller Blöcke oder Klassen deklariert hat einen Dateigültigkeitsbereich. Auf ihn kann nach seiner Deklaration in der gesamten Übersetzungseinheit zugegriffen werden. Namen mit Dateigültigkeitsbereich, die keine statischen Objekte deklarieren, werden oft als globale Namen bezeichnet.  
  
     In C++ ist der Dateigültigkeitsbereich auch als Namespacegültigkeitsbereich bekannt.  
  
-   **Klassengültigkeitsbereich** Namen von Klassenmembern haben einen Klassengültigkeitsbereich. Klassenmemberfunktionen können nur mithilfe der memberauswahloperatoren zugegriffen werden (**.** oder  **->** ) oder Pointer-to-Member-Operatoren (**.\***  oder  **-> \*** ) auf ein Objekt oder Zeiger auf ein Objekt dieser Klasse; nicht statische Klassenmemberdaten lokal für das Objekt dieser Klasse betrachtet werden. Betrachten Sie die folgende Klassendeklaration:  
  
    ```  
    class Point  
    {  
        int x;  
        int y;  
    };  
    ```  
  
     Die Klassenmember `x` und `y` werden als im Gültigkeitsbereich der Klasse `Point` betrachtet.  
  
-   **Prototypbereich** Namen, die in einem Funktionsprototyp deklariert sind nur bis zum Ende des Prototyps sichtbar. Der folgende Prototyp deklariert drei Namen (`strDestination`, `numberOfElements` und `strSource`). Diese Namen verlassen am Ende des Prototyps den gültigen Bereich:  
  
    ```  
    errno_t strcpy_s( char *strDestination, size_t numberOfElements, const char *strSource );  
    ```  
  
## <a name="hiding-names"></a>Ausblenden von Namen  
 Sie können einen Namen verbergen, indem Sie ihn in einem eingeschlossenen Block deklarieren. In der folgenden Abbildung wird `i` innerhalb des inneren Blocks neu deklariert. Dadurch wird die Variable ausgeblendet, die `i` im äußeren Blockbereich zugeordnet ist.  
  
 ![Bereich Name ausblenden Block &#45;](../cpp/media/vc38sf1.png "vc38SF1")  
Blockbereich und Ausblenden von Namen  
  
 Die in der Abbildung dargestellte Ausgabe des Programms lautet wie folgt:  
  
```  
i = 0  
i = 7  
j = 9  
i = 0  
```  
  
> [!NOTE]
>  Es wird angenommen, dass das `szWhat`-Argument im Funktionsbereich liegt. Daher wird es so behandelt, als wäre es im äußersten Block der Funktion deklariert worden.  
  
## <a name="hiding-class-names"></a>Ausblenden von Klassennamen  
 Sie können Klassennamen ausblenden, indem Sie eine Funktion, ein Objekt, eine Variable oder einen Enumerator im gleichen Bereich deklarieren. Der Klassenname kann jedoch weiterhin zugegriffen werden, wenn das Schlüsselwort vorangestellt **Klasse**.  
  
```  
// hiding_class_names.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
// Declare class Account at file scope.  
class Account  
{  
public:  
    Account( double InitialBalance )  
        { balance = InitialBalance; }  
    double GetBalance()  
        { return balance; }  
private:  
    double balance;  
};  
  
double Account = 15.37;            // Hides class name Account  
  
int main()  
{  
    class Account Checking( Account ); // Qualifies Account as   
                                       //  class name  
  
    cout << "Opening account with balance of: "  
         << Checking.GetBalance() << "\n";  
}  
//Output: Opening account with balance of: 15.37  
```  
  
> [!NOTE]
>  Für jeden Ort, für den der Klassenname (`Account`) aufgerufen wird, muss zur Unterscheidung von der dateispezifischen Account-Variable das class-Schlüsselwort verwendet werden. Diese Regel gilt nicht, wenn der Klassenname auf der linken Seite des Bereichsauflösungsoperators (::) auftritt. Namen auf der linken Seite des Bereichsauflösungsoperators gelten immer als Klassennamen.  
  
 Im folgenden Beispiel wird veranschaulicht, wie einen Zeiger auf ein Objekt des Typs deklarieren `Account` mithilfe der **Klasse** Schlüsselwort:  
  
```  
class Account *Checking = new class Account( Account );  
```  
  
 Die `Account` im Initialisierer (in Klammern) in der vorherigen Anweisung dateispezifisch und weist eigentlicher Typ ist **doppelte**.  
  
> [!NOTE]
>  Die in diesem Beispiel dargestellte Wiederverwendung von Bezeichnernamen gilt als schlechter Programmierstil.  
  
 Weitere Informationen über Zeiger finden Sie unter [Typen "Derived"](http://msdn.microsoft.com/en-us/aa14183c-02fe-4d81-95fe-beddb0c01c7c). Informationen über die Deklaration und Initialisierung von Klassenobjekten finden Sie unter [Klassen, Strukturen und Unions](../cpp/classes-and-structs-cpp.md). Informationen zum Verwenden der **neue** und **löschen** freien Speicheroperatoren, finden Sie unter [neue "und" delete](new-and-delete-operators.md).  
  
## <a name="hiding-names-with-file-scope"></a>Ausblenden von Namen mit Dateibereich  
 Sie können Namen mit Dateigültigkeitsbereich ausblenden, indem Sie explizit den gleichen Namen im Blockbereich deklarieren. Allerdings kann auf Namen mit einem Dateigültigkeitsbereich mithilfe des Bereichsauflösungsoperators (`::`) zugegriffen werden.  
  
```  
// file_scopes.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int i = 7;   // i has file scope, outside all blocks  
using namespace std;  
  
int main( int argc, char *argv[] ) {  
   int i = 5;   // i has block scope, hides i at file scope  
   cout << "Block-scoped i has the value: " << i << "\n";  
   cout << "File-scoped i has the value: " << ::i << "\n";  
}  
```  
  
```Output  
Block-scoped i has the value: 5  
File-scoped i has the value: 7  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlegende Konzepte](../cpp/basic-concepts-cpp.md)