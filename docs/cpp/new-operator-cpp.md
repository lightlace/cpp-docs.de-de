---
title: "new-Operator (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "new-Schlüsselwort [C++]"
ms.assetid: 69fee812-1c28-4882-8fda-d1ad17860004
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# new-Operator (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Weist einem Objekt oder einem Array von Objekten des Typs *type\-name* Speicher aus dem freien Speicher zu und gibt einen typisierten Zeiger ungleich 0 an das Objekt zurück.  
  
> [!NOTE]
>  Erweiterungen der Microsoft C\+\+\-Komponente bieten Unterstützung für das `new`\-Schlüsselwort, um dem vtable\-Slot Einträge hinzuzufügen.  Weitere Informationen finden Sie unter [new \(new slot in vtable\)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md).  
  
## Syntax  
  
```  
[::] new [placement] new-type-name [new-initializer]  
[::] new [placement] ( type-name ) [new-initializer]  
```  
  
## Hinweise  
 Wenn Fehler auftreten, wird von **new** der Wert Null zurückgegeben und eine Ausnahme ausgelöst. Weitere Informationen erhalten Sie unter [Die Operatoren new und delete](../cpp/new-and-delete-operators.md).  Sie können dieses Standardverhalten ändern, indem Sie eine benutzerdefinierte Ausnahmebehandlungsroutine schreiben und die Funktion der Laufzeitbibliothek [\_set\_new\_handler](../c-runtime-library/reference/set-new-handler.md) mit dem Funktionsnamen als Argument aufrufen.  
  
 Weitere Informationen zum Erstellen von Objekten im verwalteten Heap finden Sie unter [gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md).  
  
 Wenn **new** verwendet wird, um für ein C\+\+\-Klassenobjekt Speicher zuzuweisen, wird der Konstruktor des Objekts aufgerufen, nachdem der Arbeitsspeicher zugewiesen wurde.  
  
 Verwenden Sie den [delete](../cpp/delete-operator-cpp.md)\-Operator, um den Arbeitsspeicher freizugeben, der mit dem **new**\-Operator zugewiesen wurde.  
  
 Im folgenden Beispiel wird ein zweidimensionales Array der Größe `dim` durch 10 zugewiesen und dann freigegeben.  Beim Zuweisen eines mehrdimensionalen Arrays müssen alle Dimensionen mit Ausnahme der ersten Konstantenausdrücke sein, die zu positiven Werten ausgewertet werden. Die Arraydimension ganz links kann ein beliebiger Ausdruck sein, der zu einem positiven Wert ausgewertet wird.  Wenn Sie ein Array mithilfe des Operators **new** zuweisen, kann die erste Dimension null sein. Der Operator **new** gibt einen eindeutigen Zeiger zurück.  
  
```  
char (*pchar)[10] = new char[dim][10];  
delete [] pchar;  
```  
  
 Der *Typname* darf keine **const**, `volatile`, Klassendeklarationen oder Deklarationen einer Enumeration enthalten.  Daher ist der folgende Ausdruck ungültig:  
  
```  
volatile char *vch = new volatile char[20];  
```  
  
 Vom Operator **new** werden keine Referenztypen zugewiesen, da diese keine Objekte sind.  
  
 Der Operator **new** darf nicht zum Zuweisen einer Funktion verwendet werden. Er kann jedoch verwendet werden, um Funktionen Zeiger zuzuordnen.  Im folgenden Beispiel wird ein Array von sieben Zeigern auf Funktionen, die ganze Zahlen zurückgeben, zugewiesen und dann freigegeben.  
  
```  
int (**p) () = new (int (*[7]) ());  
delete *p;  
```  
  
 Wenn Sie den Operator **new** ohne zusätzliche Argumente verwenden und die Kompilierung mit der Option [\/GX](../build/reference/gx-enable-exception-handling.md), [\/EHa](../build/reference/eh-exception-handling-model.md) oder [\/EHs](../build/reference/eh-exception-handling-model.md) durchführen, wird vom Compiler Code zum Aufrufen des Operators **delete** generiert, sobald der Konstruktor eine Ausnahme auslöst.  
  
 In der folgenden Liste werden die Grammatikelemente von **new** beschrieben:  
  
 *Platzierung*  
 Stellt eine Methode zur Übergabe zusätzlicher Argumente bereit, wenn Sie **new** überladen.  
  
 *Typname*  
 Gibt den zuzuweisenden Typ an. Es kann entweder ein integrierter oder ein benutzerdefinierter Typ sein.  Eine komplizierte Typspezifikation können Sie in Klammern einschließen, um die Reihenfolge der Bindung zu erzwingen.  
  
 *Initialisierer*  
 Stellt einen Wert für das initialisierte Objekt bereit.  Für Arrays können keine Initialisierer angegeben werden.  Mit dem Operator **new** werden nur dann Objektarrays erstellt, wenn die Klasse über einen Standardkonstruktor verfügt.  
  
## Beispiel  
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
  
## Beispiel  
 Wenn Sie das neue Format für die Platzierung des Operators **new** verwenden \(ein Format, das neben der Belegungsgröße auch Argumente enthält\), wird vom Compiler kein Platzierungsformat des Operators **delete** unterstützt, wenn der Konstruktor eine Ausnahme auslöst.  Zum Beispiel:  
  
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
  
## Initialisieren von mit „new“ zugeordneten Objekten  
 Ein optionales Feld *Initialisierer* ist in der Grammatik für den **new**\-Operator enthalten.  Dadurch können neue Objekte mit benutzerdefinierten Konstruktoren initialisiert werden.  Weitere Informationen darüber, wie die Initialisierung durchgeführt wird, finden Sie unter [Initialisierer](../cpp/initializers.md).  Das folgende Beispiel veranschaulicht, wie Sie einen Initialisierungsausdruck mit dem **new**\-Operator verwenden:  
  
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
  
 In diesem Beispiel wird das Objekt `CheckingAcct` mithilfe des Operators **new** zugeordnet, aber es wird keine Standardinitialisierung angegeben.  Deshalb wird der Standardkonstruktor für die `Acct()`\-Klasse aufgerufen.  Anschließend wird das Objekt `SavingsAcct` auf die gleiche Weise zugeordnet, mit der Ausnahme, dass es explizit mit 34,98 initialisiert wird.  Da 34.98 den Typ **double** aufweist, wird der Konstruktor, der ein Argument dieses Typs akzeptiert, aufgerufen, um die Initialisierung zu bearbeiten.  Schließlich wird der Nichtklassentyp `HowMuch` mit 43,0 initialisiert.  
  
 Wenn ein Objekt einen Klassentyp besitzt und diese Klasse Konstruktoren \(wie im vorhergehenden Beispiel\) enthält, kann das Objekt nur dann mit dem **new**\-Operator initialisiert werden, wenn eine dieser Bedingungen erfüllt ist:  
  
-   Die Argumente, die im Initialisierer bereitgestellt werden, stimmen mit denen eines Konstruktors überein.  
  
-   Die Klasse verfügt über einen Standardkonstruktor \(einen Konstruktor, der ohne Argumente aufgerufen werden kann\).  
  
 Zugriffssteuerung und Mehrdeutigkeitssteuerung werden auf `operator new` und auf den Konstruktoren nach den Regeln ausgeführt, die in [Mehrdeutigkeit](assetId:///0b399cab-40a7-4e79-9278-05f40139a0e1) und [Initialisierung mit speziellen Memberfunktionen](assetId:///82223d73-64cb-4923-b678-78f9568ff3ca) festgelegt sind.  
  
 Es kann keine explizite Initialisierung pro Element erfolgen, wenn Arrays mithilfe des **new**\-Operators zuordnet werden. Nur der Standardkonstruktor wird aufgerufen, wenn er vorhanden ist.  Weitere Informationen finden Sie unter [Standardargumente](../cpp/default-arguments.md).  
  
 Wenn die Speicherbelegung fehlschlägt \(`operator new` gibt den Wert 0 \(null\) zurück\), wird keine Initialisierung ausgeführt.  Dies schützt vor Versuchen, Daten zu initialisieren, die nicht vorhanden sind.  
  
 Wie bei Funktionsaufrufen ist auch bei initialisierten Ausdrücken die Reihenfolge der Auswertung nicht festgelegt.  Darüber hinaus sollten Sie sich nicht darauf verlassen, dass diese Ausdrücke vollständig ausgewertet werden, bevor die Speicherbelegung ausgeführt wird.  Wenn die Speicherbelegung fehlschlägt und der **new**\-Operator 0 \(null\) zurückgibt, werden einige Ausdrücke im Initialisierer möglicherweise nicht vollständig ausgewertet.  
  
## Lebensdauer von mit „new“ zugeordneten Objekten  
 Objekte, die mit dem **new**\-Operator zugeordnet werden, werden nicht zerstört, wenn der Gültigkeitsbereich, in dem sie definiert sind, beendet wird.  Da der **new**\-Operator einen Zeiger auf Objekte zurückgibt, die er zuordnet, muss das Programm einen Zeiger mit passendem Gültigkeitsbereich definieren, um auf diese Objekte zuzugreifen.  Zum Beispiel:  
  
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
  
## Funktionsweise von „new“  
 Der *Zuweisungsausdruck*, d. h. der Ausdruck, der den **new**\-Operator enthält, führt drei Aktionen aus:  
  
-   Sucht und reserviert Speicher für das zuzuweisende Objekt bzw. die zuzuweisenden Objekte.  Nach Abschluss dieser Phase wird die richtige Menge an Speicherplatz zugewiesen. Es handelt sich jedoch noch nicht um ein Objekt.  
  
-   Initialisiert das\/die Objekt\(e\).  Sobald die Initialisierung abgeschlossen wurde, sind genügend Informationen vorhanden, damit der zugeordnete Speicher ein Objekt sein kann.  
  
-   Gibt einen Zeiger auf Objekte eines Zeigertyps zurück, der von *new\-type\-name* oder *type\-name* abgeleitet wurde.  Das Programm verwendet diesen Zeiger, um auf das neu zugeordnete Objekt zuzugreifen.  
  
 Mit dem **new**\-Operator wird die `operator new`\-Funktion aufgerufen.  Für Arrays eines beliebigen Typs und für Objekte, die nicht vom Typ **class**, `struct` oder **union** sind, wird die globale Funktion **::operator new** aufgerufen, um Speicher zuzuweisen.  Klassentypobjekte können ihre eigene statische `operator new`\-Memberfunktion auf Basis einer einzelnen Klasse definieren.  
  
 Wenn der Compiler den **new**\-Operator zum Zuweisen eines Objekts vom Typ `type` erkennt, ruft er `type`**::operator new\( sizeof\(** `type` **\) \)** auf. Wenn kein benutzerdefinierter `operator new`\-Parameter festgelegt ist, wird **::operator new\( sizeof\(** `type` **\) \)** aufgerufen.  Daher kann der **new**\-Operator die richtige Menge an Speicherplatz für das Objekt zuweisen.  
  
> [!NOTE]
>  Das Argument für `operator new` ist vom Typ **size\_t**.  Dieser Typ ist in DIRECT.H, MALLOC.H, MEMORY.H, SEARCH.H, STDDEF.H, STDIO.H, STDLIB.H, STRING.H und TIME.H definiert.  
  
 Eine Option in der Grammatik ermöglicht die Festlegung der *Platzierung* \(weitere Informationen hierzu finden Sie in der Grammatik für [neuer Operator](../cpp/new-operator-cpp.md)\).  Der *placement*\-Parameter kann nur für benutzerdefinierte Implementierungen von `operator new` verwendet werden. Damit können weitere Informationen an `operator new` übergeben werden.  Ein Ausdruck mit einem Feld für *Platzierung* wie `T *TObject = new ( 0x0040 ) T;` wird in `T *TObject = T::operator new( sizeof( T ), 0x0040 );` übersetzt, wenn die Klasse "T" den Member\-Operator "new" hat. Andernfalls wird der Ausdruck in `T *TObject = ::operator new( sizeof( T ), 0x0040 );` übersetzt.  
  
 Das Feld *Platzierung* war ursprünglich dazu gedacht, die Zuordnung hardwareabhängiger Objekte zu benutzerspezifischen Adressen zu ermöglichen.  
  
> [!NOTE]
>  Obwohl das obige Beispiel nur ein Argument im Feld *Platzierung* veranschaulicht, gibt es keine Beschränkung, wie viele zusätzliche Argumente auf diese Weise an `operator new` übergeben werden können.  
  
 Auch wenn `operator new` für einen Klassentyp definiert wurde, kann der globale Operator verwendet werden, indem Sie das Format in diesem Beispiel nutzen:  
  
```  
T *TObject =::new TObject;  
```  
  
 Der Bereichsauflösungsoperator \(`::`\) erzwingt die Verwendung des globalen **new**\-Operators.  
  
## Siehe auch  
 [Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [operator new\-Funktion](../misc/operator-new-function.md)