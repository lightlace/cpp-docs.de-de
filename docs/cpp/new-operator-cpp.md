---
title: new-Operator (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: new keyword [C++]
ms.assetid: 69fee812-1c28-4882-8fda-d1ad17860004
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 98a6a535071246f75d877e7f63d3a0e9d86053be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="new-operator-c"></a>new-Operator (C++)
Belegt Speicher für ein Objekt oder Array von Objekten des *Typname* aus dem freien Speicher und einen typisierten Zeiger ungleich NULL für das Objekt zurückgegeben.  
  
> [!NOTE]
>  Erweiterungen der Microsoft C++-Komponente bieten Unterstützung für das `new`-Schlüsselwort, um dem vtable-Slot Einträge hinzuzufügen. Weitere Informationen finden Sie unter [new (neuer Slot in Vtable)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
[::] new [placement] new-type-name [new-initializer]  
[::] new [placement] ( type-name ) [new-initializer]  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn dies nicht gelingt, **neue** gibt NULL oder eine Ausnahme auslöst, finden Sie unter [die neue "und" delete](../cpp/new-and-delete-operators.md) für Weitere Informationen. Sie können dieses Standardverhalten ändern, indem Sie eine benutzerdefinierte Ausnahmebehandlungsroutine schreiben und Aufrufen der [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) Run-Time Library-Funktion mit dem Funktionsnamen als Argument.  
  
 Informationen zum Erstellen von Objekten im verwalteten Heaps finden Sie unter [Gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md).  
  
 Wenn **neue** wird verwendet, um für ein C++-Klassenobjekt Speicher, den Konstruktor des Objekts wird aufgerufen, nachdem der Speicher belegt wird.  
  
 Verwenden der [löschen](../cpp/delete-operator-cpp.md) Operator mit belegten Speicher freigeben der **neue** Operator.  
  
 Im folgenden Beispiel wird ein zweidimensionales Array der Größe `dim` durch 10 zugewiesen und dann freigegeben. Beim Zuweisen eines mehrdimensionalen Arrays müssen alle Dimensionen mit Ausnahme der ersten Konstantenausdrücke sein, die zu positiven Werten ausgewertet werden. Die Arraydimension ganz links kann ein beliebiger Ausdruck sein, der zu einem positiven Wert ausgewertet wird. Beim Zuweisen eines Arrays mithilfe der **neue** -Operator, in die erste Dimension kann 0 (null) – die **neue** Operator gibt einen eindeutigen Zeiger zurück.  
  
```  
char (*pchar)[10] = new char[dim][10];  
delete [] pchar;  
```  
  
 Die *Typname* sind keine **const**, `volatile`, Klassendeklarationen oder Deklarationen einer Enumeration. Daher ist der folgende Ausdruck ungültig:  
  
```  
volatile char *vch = new volatile char[20];  
```  
  
 Die **neue** Operator keine Referenztypen zugewiesen, da es keine Objekte sind.  
  
 Die **neue** Operator kann nicht zum Zuweisen einer Funktion verwendet werden, aber es kann verwendet werden, um Funktionen Zeiger zuzuordnen. Im folgenden Beispiel wird ein Array von sieben Zeigern auf Funktionen, die ganze Zahlen zurückgeben, zugewiesen und dann freigegeben.  
  
```  
int (**p) () = new (int (*[7]) ());  
delete *p;  
```  
  
 Wenn Sie den Operator **neue** ohne zusätzliche Argumente verwenden und die Kompilierung mit der [/GX](../build/reference/gx-enable-exception-handling.md), [/EHa](../build/reference/eh-exception-handling-model.md), oder [/EHs](../build/reference/eh-exception-handling-model.md) Option der Compiler wird Generieren von Code zum Aufrufen des Operators **löschen** der Konstruktor eine Ausnahme auslöst.  
  
 Die folgende Liste beschreibt die Grammatikelemente von **neue**:  
  
 *Platzierung*  
 Bietet eine Möglichkeit, zusätzliche Argumente übergeben, wenn Sie überladen **neue**.  
  
 *Typname*  
 Gibt den zuzuweisenden Typ an. Es kann entweder ein integrierter oder ein benutzerdefinierter Typ sein. Eine komplizierte Typspezifikation können Sie in Klammern einschließen, um die Reihenfolge der Bindung zu erzwingen.  
  
 *initializer*  
 Stellt einen Wert für das initialisierte Objekt bereit. Für Arrays können keine Initialisierer angegeben werden. Die **neue** -Operator erstellt Arrays von Objekten nur, wenn die Klasse über einen Standardkonstruktor verfügt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel werden ein Zeichenarray und ein Objekt der Klasse `CName` zugewiesen und dann wieder freigegeben.  
  
```  
// expre_new_Operator.cpp  
// compile with: /EHsc  
#include <string.h>  
  
class CName {  
public:  
   enum {  
      sizeOfBuffer = 256  
   };  
  
   char m_szFirst[sizeOfBuffer];  
   char m_szLast[sizeOfBuffer];  
  
public:  
   void SetName(char* pszFirst, char* pszLast) {  
     strcpy_s(m_szFirst, sizeOfBuffer, pszFirst);  
     strcpy_s(m_szLast, sizeOfBuffer, pszLast);  
   }  
  
};  
  
int main() {  
   // Allocate memory for the array  
   char* pCharArray = new char[CName::sizeOfBuffer];  
   strcpy_s(pCharArray, CName::sizeOfBuffer, "Array of characters");  
  
   // Deallocate memory for the array  
   delete [] pCharArray;             
   pCharArray = NULL;  
  
   // Allocate memory for the object  
   CName* pName = new CName;  
   pName->SetName("Firstname", "Lastname");  
  
   // Deallocate memory for the object  
   delete pName;  
   pName = NULL;  
}  
```  
  
## <a name="example"></a>Beispiel  
 Bei Verwendung die neuen Positionierungsform des der **neue** -Operator, das Formular mit Argumenten, die zusätzlich zur Größe der speicherbelegung, der Compiler unterstützt keine Positionierungsform des der **löschen** Operator Wenn die Konstruktors löst eine Ausnahme aus. Zum Beispiel:  
  
```  
// expre_new_Operator2.cpp  
// C2660 expected  
class A {  
public:  
   A(int) { throw "Fail!"; }  
};  
void F(void) {  
   try {  
      // heap memory pointed to by pa1 will be deallocated  
      // by calling ::operator delete(void*).  
      A* pa1 = new A(10);  
   } catch (...) {  
   }  
   try {  
      // This will call ::operator new(size_t, char*, int).  
      // When A::A(int) does a throw, we should call  
      // ::operator delete(void*, char*, int) to deallocate  
      // the memory pointed to by pa2.  Since  
      // ::operator delete(void*, char*, int) has not been implemented,  
      // memory will be leaked when the deallocation cannot occur.  
  
      A* pa2 = new(__FILE__, __LINE__) A(20);  
   } catch (...) {  
   }  
}  
  
int main() {  
   A a;  
}  
```  
  
## <a name="initializing-object-allocated-with-new"></a>Initialisieren von mit „new“ zugeordneten Objekten  
 Ein optionales *Initialisierer* Feld ist in der Grammatik für enthalten die **neue** Operator. Dadurch können neue Objekte mit benutzerdefinierten Konstruktoren initialisiert werden. Weitere Informationen dazu, wie die Initialisierung durchgeführt wird, finden Sie unter [Initialisierer](../cpp/initializers.md). Das folgende Beispiel veranschaulicht, wie Sie einen Initialisierungsausdruck mit dem **neue** Operator:  
  
```  
// expre_Initializing_Objects_Allocated_with_new.cpp  
class Acct  
{  
public:  
    // Define default constructor and a constructor that accepts  
    //  an initial balance.  
    Acct() { balance = 0.0; }  
    Acct( double init_balance ) { balance = init_balance; }  
private:  
    double balance;  
};  
  
int main()  
{  
    Acct *CheckingAcct = new Acct;  
    Acct *SavingsAcct = new Acct ( 34.98 );  
    double *HowMuch = new double ( 43.0 );  
    // ...  
}  
```  
  
 In diesem Beispiel wird das Objekt `CheckingAcct` erhält mithilfe der **neue** -Operator, aber keine standardinitialisierung angegeben ist. Deshalb wird der Standardkonstruktor für die `Acct()`-Klasse aufgerufen. Anschließend wird das Objekt `SavingsAcct` auf die gleiche Weise zugeordnet, mit der Ausnahme, dass es explizit mit 34,98 initialisiert wird. Da 34.98 Typ **doppelte**, des Konstruktors, der ein des Typs Argument wird aufgerufen, um die Initialisierung zu bearbeiten. Schließlich wird der Nichtklassentyp `HowMuch` mit 43,0 initialisiert.  
  
 Wenn ein Objekt eines Klassentyps ist, und diese Klasse verfügt über Konstruktoren (wie im obigen Beispiel), kann das Objekt initialisiert werden, durch die **neue** Operator nur, wenn eine der folgenden Bedingungen erfüllt ist:  
  
-   Die Argumente, die im Initialisierer bereitgestellt werden, stimmen mit denen eines Konstruktors überein.  
  
-   Die Klasse verfügt über einen Standardkonstruktor (einen Konstruktor, der ohne Argumente aufgerufen werden kann).  
  
 Keine pro Element explizite Initialisierung kann erfolgen, beim Zuordnen von mithilfe Arrays der **neue** Operator; nur der Standardkonstruktor wird aufgerufen, sofern vorhanden. Finden Sie unter [Standardargumente](../cpp/default-arguments.md) für Weitere Informationen.  
  
 Wenn die Speicherbelegung fehlschlägt (`operator new` gibt den Wert 0 (null) zurück), wird keine Initialisierung ausgeführt. Dies schützt vor Versuchen, Daten zu initialisieren, die nicht vorhanden sind.  
  
 Wie bei Funktionsaufrufen ist auch bei initialisierten Ausdrücken die Reihenfolge der Auswertung nicht festgelegt. Darüber hinaus sollten Sie sich nicht darauf verlassen, dass diese Ausdrücke vollständig ausgewertet werden, bevor die Speicherbelegung ausgeführt wird. Wenn die speicherbelegung fehlschlägt und die **neue** Operator gibt 0 (null) zurück, die einige Ausdrücke im Initialisierer möglicherweise nicht vollständig ausgewertet.  
  
## <a name="lifetime-of-objects-allocated-with-new"></a>Lebensdauer von mit „new“ zugeordneten Objekten  
 Mit zugeordneten Objekten der **neue** Operator nicht zerstört, wenn der Bereich, in dem sie definiert sind, beendet wird. Da die **neue** Operator gibt einen Zeiger auf die Objekte, die er zuordnet, die Anwendung muss einen Zeiger mit passendem Gültigkeitsbereich den Zugriff auf diese Objekte definieren. Zum Beispiel:  
  
```  
// expre_Lifetime_of_Objects_Allocated_with_new.cpp  
// C2541 expected  
int main()  
{  
    // Use new operator to allocate an array of 20 characters.  
    char *AnArray = new char[20];  
  
    for( int i = 0; i < 20; ++i )  
    {  
        // On the first iteration of the loop, allocate  
        //  another array of 20 characters.  
        if( i == 0 )  
        {  
            char *AnotherArray = new char[20];  
        }  
    }  
  
    delete [] AnotherArray; // Error: pointer out of scope.  
    delete [] AnArray;      // OK: pointer still in scope.  
}  
```  
  
 Sobald der Zeiger `AnotherArray` den Gültigkeitsbereich in dem Beispiel verlässt, kann das Objekt nicht mehr gelöscht werden.  
  
## <a name="how-new-works"></a>Funktionsweise von „new“  
 Die *Zuweisungsausdruck* – der Ausdruck enthält das **neue** Operator – bewirkt drei Dinge:  
  
-   Sucht und reserviert Speicher für das zuzuweisende Objekt bzw. die zuzuweisenden Objekte. Nach Abschluss dieser Phase wird die richtige Menge an Speicherplatz zugewiesen. Es handelt sich jedoch noch nicht um ein Objekt.  
  
-   Initialisiert das/die Objekt(e). Sobald die Initialisierung abgeschlossen wurde, sind genügend Informationen vorhanden, damit der zugeordnete Speicher ein Objekt sein kann.  
  
-   Gibt ein Zeiger auf Objekte eines Zeigertyps abgeleitet *neuen Typnamen* oder *Typname*. Das Programm verwendet diesen Zeiger, um auf das neu zugeordnete Objekt zuzugreifen.  
  
 Die **neue** -Operator Ruft die Funktion `operator new`. Für Arrays eines beliebigen Typs und für Objekte, die nicht von **Klasse**, `struct`, oder **Union** Typen, die eine globale Funktion **:: new-Operator**, wird aufgerufen, um Speicher zu belegen. Klassentypobjekte können ihre eigene statische `operator new`-Memberfunktion auf Basis einer einzelnen Klasse definieren.  
  
 Wenn der Compiler erkennt die **neue** Operator, um ein Objekt des Typs zuordnen `type`, einen Aufruf von ausgestellten `type` **:: new-Operator ("sizeof" (** `type` **))**  oder, wenn keine benutzerdefinierten `operator new` definiert ist, **:: new-Operator (Sizeof (** `type` **))**. Aus diesem Grund die **neue** -Operator die richtige Menge an Arbeitsspeicher für das Objekt zuordnen kann.  
  
> [!NOTE]
>  Das Argument für `operator new` ist vom Typ **Size_t**. Dieser Typ ist in DIRECT.H, MALLOC.H, MEMORY.H, SEARCH.H, STDDEF.H, STDIO.H, STDLIB.H, STRING.H und TIME.H definiert.  
  
 Eine Option in der Grammatik ermöglicht die Festlegung der *Platzierung* (finden Sie in der Grammatik für [new-Operator](../cpp/new-operator-cpp.md)). Die *Platzierung* Parameter kann verwendet werden, nur für benutzerdefinierte Implementierungen der `operator new`; damit können weitere Informationen zu übergebenden `operator new`. Ein Ausdruck mit einem *Platzierung* Feld, z. B. `T *TObject = new ( 0x0040 ) T;` übersetzt `T *TObject = T::operator new( sizeof( T ), 0x0040 );` Wenn die Klasse T Memberoperator neue, andernfalls hat `T *TObject = ::operator new( sizeof( T ), 0x0040 );`.  
  
 Der ursprünglichen Absicht der *Platzierung* Feld wurde damit hardwareabhängig Objekte am benutzerspezifischen Adressen zugewiesen werden können.  
  
> [!NOTE]
>  Obwohl das obige Beispiel nur ein Argument im zeigt die *Platzierung* Feld, besteht keine Einschränkung auf wie viele zusätzliche Argumente können, um übergeben werden `operator new` auf diese Weise.  
  
 Auch wenn `operator new` für einen Klassentyp definiert wurde, kann der globale Operator verwendet werden, indem Sie das Format in diesem Beispiel nutzen:  
  
```  
T *TObject =::new TObject;  
```  
  
 Der Bereichsauflösungsoperator (`::`) erzwingt die Verwendung des globalen **neue** Operator.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke mit Unäroperatoren](../cpp/expressions-with-unary-operators.md)   
 [Stichwörter](../cpp/keywords-cpp.md)   
 [neue und "delete"](../cpp/new-and-delete-operators.md)