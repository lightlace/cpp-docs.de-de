---
title: "Löschen von Operator (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: delete_cpp
dev_langs: C++
helpviewer_keywords:
- delete keyword [C++], syntax
- delete keyword [C++], deallocating objects
- delete keyword [C++]
ms.assetid: de39c900-3f57-489c-9598-dcb73c4b3930
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 36da346329341221d43af2ec96aa17be4f819bf8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="delete-operator-c"></a>delete-Operator (C++)
Gibt einen Speicherblock frei.  
  
## <a name="syntax"></a>Syntax  
  
```  
[::] delete cast-expression  
[::] delete [ ] cast-expression  
```  
  
## <a name="remarks"></a>Hinweise  
 Die *Umwandlungsausdruck* Argument muss ein Zeiger auf einen Block des Arbeitsspeichers, die zuvor für ein Objekt erstellt, mit der [new-Operator](../cpp/new-operator-cpp.md). Die **löschen** -Operator weist ein Ergebnis vom Typ `void` und daher keinen Wert zurückgibt. Zum Beispiel:  
  
```  
CDialog* MyDialog = new CDialog;  
// use MyDialog  
delete MyDialog;  
```  
  
 Mit **löschen** für einen Zeiger auf ein Objekt, das nicht mit "" zugeordneten **neue** führt zu unvorhersehbaren Ergebnissen. Sie können allerdings verwenden **löschen** auf einen Zeiger mit dem Wert 0. Diese Bereitstellung bedeutet, dass, wenn **neue** gibt 0 zurück, bei einem Fehler, und löschen das Ergebnis eines Fehlers bei **neue** Vorgang harmlos ist. Finden Sie unter [die neue "und" delete](../cpp/new-and-delete-operators.md) für Weitere Informationen.  
  
 Die **neue** und **löschen** Operatoren können auch für integrierte Typen, einschließlich Arrays verwendet werden. Wenn `pointer` auf ein Array verweist, platzieren Sie leere Klammern vor `pointer`:  
  
```  
int* set = new int[100];  
//use set[]  
delete [] set;  
```  
  
 Mithilfe der **löschen** Operator auf ein Objekt wird dessen Speicher freigegeben. Ein Programm, das einen Zeiger dereferenziert, nachdem das Objekt gelöscht wurde, kann zu unvorhersehbaren Ergebnissen führen oder abstürzen.  
  
 Wenn **löschen** wird verwendet, um Arbeitsspeicher für ein C++-Klassenobjekt freizugeben, der Destruktor des Objekts wird aufgerufen, bevor der Speicher des Objekts freigegeben wird (wenn das Objekt einen Destruktor aufweist).  
  
 Wenn der Operand für den **löschen** Operator ist ein änderbarer l-Wert, dessen Wert ist nicht definiert, nachdem das Objekt gelöscht wird.  
  
## <a name="using-delete"></a>Verwenden von "delete"  
 Es gibt zwei syntaktische Varianten für den [delete-Operator](../cpp/delete-operator-cpp.md): eine für einzelne Objekte und die andere für Arrays von Objekten. Das folgende Codefragment zeigt, wie sich diese unterscheiden:  
  
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
  
 Die folgenden zwei Fälle führen zu undefinierten Ergebnissen: Verwenden der Arrayform von "delete (delete [ ])" für ein Objekt und Verwenden der Nichtarrayform von "delete" für ein Array.  
  
## <a name="example"></a>Beispiel  
 Beispiele für die Verwendung von **löschen**, finden Sie unter [new-Operator](../cpp/new-operator-cpp.md).  
  
## <a name="how-delete-works"></a>Funktionsweise von „delete“  
 Der Delete-Operator Ruft die Funktion **Delete-Operator**.  
  
 Für Objekte nicht vom Klassentyp ([Klasse](../cpp/class-cpp.md), [Struktur](../cpp/struct-cpp.md), oder [Union](../cpp/unions.md)), wird der globale Delete-Operator aufgerufen. Für Objekte des Klassentyps wird der Name der Funktion zum Aufheben der Zuordnung im globalen Bereich aufgelöst, wenn der Löschausdruck mit dem unären Bereichsauflösungsoperator (::) beginnt. Andernfalls ruft der delete-Operator den Destruktor für ein Objekt vor dem Freigeben des Speichers auf (wenn der Zeiger nicht NULL ist). Der delete-Operator kann auf Basis einer einzelnen Klasse definiert werden; wenn keine solche Definition für eine bestimmte Klasse vorliegt, wird der globale delete-Operator aufgerufen. Wenn der Löschausdruck verwendet wird, um ein Klassenobjekt freizugeben, dessen statischer Typ einen virtuellen Destruktor aufweist, wird die Funktion zum Aufheben der Zuordnung vom virtuellen Destruktor des dynamischen Typs des Objekts aufgelöst.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke mit Unäroperatoren](../cpp/expressions-with-unary-operators.md)   
 [Stichwörter](../cpp/keywords-cpp.md)   
 [Operatoren "new" und "delete"](../cpp/new-and-delete-operators.md)   
 
