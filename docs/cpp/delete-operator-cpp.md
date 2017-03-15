---
title: "delete-Operator (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "delete_cpp"
  - "delete"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "delete-Schlüsselwort [C++]"
  - "delete-Schlüsselwort [C++], Freigeben von Objekten"
  - "delete-Schlüsselwort [C++], Syntax"
ms.assetid: de39c900-3f57-489c-9598-dcb73c4b3930
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# delete-Operator (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt einen Speicherblock frei.  
  
## Syntax  
  
```  
[::] delete cast-expression  
[::] delete [ ] cast-expression  
```  
  
## Hinweise  
 Das *cast\-expression*\-Argument muss ein Zeiger auf einen Speicherblock sein, der vorher einem Objekt zugeordnet wurde, das mit dem [new\-Operator](../cpp/new-operator-cpp.md) erstellt wurde.  Der **delete**\-Operator weist ein Ergebnis vom Typ `void` auf und gibt daher keinen Wert zurück.  Zum Beispiel:  
  
```  
CDialog* MyDialog = new CDialog;  
// use MyDialog  
delete MyDialog;  
```  
  
 Das Verwenden von **delete** für einen Zeiger auf ein Objekt, das nicht mit **new** zugeordnet ist, führt zu unvorhersehbaren Ergebnissen.  Sie können **delete** jedoch für einen Zeiger mit dem Wert 0 \(null\) verwenden.  Diese Bereitstellung bedeutet Folgendes: Wenn **new** bei einem Fehler 0 \(null\) zurückgibt, ist das Löschen des Ergebnisses eines **new**\-Vorgangs, bei dem ein Fehler aufgetreten ist, ungefährlich.  Weitere Informationen finden Sie unter [Die Operatoren new und delete](../cpp/new-and-delete-operators.md).  
  
 Die Operatoren **new** und **delete** können außerdem für integrierte Typen, einschließlich Arrays, verwendet werden.  Wenn `pointer` auf ein Array verweist, platzieren Sie leere Klammern vor `pointer`:  
  
```  
int* set = new int[100];  
//use set[]  
delete [] set;  
```  
  
 Durch das Verwenden des **delete**\-Operators auf einem Objekt wird dessen Speicher freigegeben.  Ein Programm, das einen Zeiger dereferenziert, nachdem das Objekt gelöscht wurde, kann zu unvorhersehbaren Ergebnissen führen oder abstürzen.  
  
 Wenn **delete** verwendet wird, um Arbeitsspeicher für ein C\+\+\-Klassenobjekt freizugeben, wird der Destruktor des Objekts aufgerufen, bevor der Speicher des Objekts freigegeben wird \(wenn das Objekt einen Destruktor aufweist\).  
  
 Wenn der Operand für den **delete**\-Operator ein änderbarer lvalue ist, ist dessen Wert nicht definiert, nachdem das Objekt gelöscht wird.  
  
## Verwenden von "delete"  
 Es gibt zwei syntaktische Varianten für den [delete\-Operator](../cpp/delete-operator-cpp.md): eine für einzelne Objekte und eine für Objektarrays.  Das folgende Codefragment zeigt, wie sich diese unterscheiden:  
  
```  
// expre_Using_delete.cpp  
struct UDType   
{  
};  
  
int main()  
{  
   // Allocate a user-defined object, UDObject, and an object  
   //  of type double on the free store using the  
   //  new operator.  
   UDType *UDObject = new UDType;  
   double *dObject = new double;  
   // Delete the two objects.  
   delete UDObject;  
   delete dObject;   
   // Allocate an array of user-defined objects on the  
   // free store using the new operator.  
   UDType (*UDArr)[7] = new UDType[5][7];  
   // Use the array syntax to delete the array of objects.  
   delete [] UDArr;  
}  
```  
  
 Die folgenden zwei Fälle führen zu undefinierten Ergebnissen: Verwenden der Arrayform von "delete \(delete \[ \]\)" für ein Objekt und Verwenden der Nichtarrayform von "delete" für ein Array.  
  
## Beispiel  
 Beispiele zur Verwendung von **delete** finden Sie unter [new\-Operator](../cpp/new-operator-cpp.md).  
  
## Funktionsweise von „delete“  
 Der [delete](../cpp/delete-operator-cpp.md)\-Operator ruft die Funktion [operator delete](../misc/operator-delete-function.md) auf.  
  
 Für Objekte, die nicht den Klassentyp \([class](../cpp/class-cpp.md), [struct](../cpp/struct-cpp.md) oder [union](../cpp/unions.md)\) aufweisen, wird der globale delete\-Operator aufgerufen.  Für Objekte des Klassentyps wird der Name der Funktion zum Aufheben der Zuordnung im globalen Bereich aufgelöst, wenn der Löschausdruck mit dem unären Bereichsauflösungsoperator \(::\) beginnt.  Andernfalls ruft der delete\-Operator den Destruktor für ein Objekt vor dem Freigeben des Speichers auf \(wenn der Zeiger nicht NULL ist\).  Der delete\-Operator kann auf Basis einer einzelnen Klasse definiert werden; wenn keine solche Definition für eine bestimmte Klasse vorliegt, wird der globale delete\-Operator aufgerufen.  Wenn der Löschausdruck verwendet wird, um ein Klassenobjekt freizugeben, dessen statischer Typ einen virtuellen Destruktor aufweist, wird die Funktion zum Aufheben der Zuordnung vom virtuellen Destruktor des dynamischen Typs des Objekts aufgelöst.  
  
## Siehe auch  
 [Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [Operatoren "new" und "delete"](../cpp/new-and-delete-operators.md)   
 [operator delete\-Funktion](../misc/operator-delete-function.md)