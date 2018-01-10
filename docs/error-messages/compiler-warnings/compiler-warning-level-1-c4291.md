---
title: Compilerwarnung (Stufe 1) C4291 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4291
dev_langs: C++
helpviewer_keywords: C4291
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a1c03e12805c35ce04322a7ffb4d48499a9a9f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4291"></a>Compilerwarnung (Stufe 1) C4291
'Declaration': keine übereinstimmenden Delete-Operator gefunden; Speicher wird nicht freigegeben werden, wenn die Initialisierung eine Ausnahme auslöst.  
  
 Eine Platzierung [neue](../../cpp/new-operator-cpp.md) wird verwendet, für das es keine Platzierung [löschen](../../cpp/delete-operator-cpp.md).  
  
 Wenn belegt für ein Objekt mit dem Operator **neue**, den Konstruktor des Objekts aufgerufen wird. Wenn der Konstruktor eine Ausnahme auslöst, sollte der Speicher, der für das Objekt zugewiesen wurde freigegeben werden. Dies kann nicht erfolgen, wenn ein Operator **löschen** Funktion vorhanden ist, der den Operator entspricht **neue**.  
  
 Wenn Sie den Operator **neue** ohne zusätzliche Argumente und die Kompilierung mit [/GX](../../build/reference/gx-enable-exception-handling.md), [/EHs](../../build/reference/eh-exception-handling-model.md), oder/EHa-Optionen zum Aktivieren der Ausnahmebehandlung, des Compilers generiert Code hinzu Aufrufoperator **löschen** der Konstruktor eine Ausnahme auslöst.  
  
 Bei Verwendung von Format für die Platzierung von der **neue** -Operator (die Form mit Argumenten, die zusätzlich zur Größe der Zuordnung) und den Konstruktor des Objekts eine Ausnahme auslöst, generiert der Compiler Code zum Aufrufen des Operators noch**löschen**; aber es wird nur der Fall, wenn eine Form der Platzierung des Operators **löschen** vorhanden ist, entspricht das Format für die Platzierung des Operators **neue** , die den Arbeitsspeicher zugeordnet. Zum Beispiel:  
  
```  
// C4291.cpp  
// compile with: /EHsc /W1  
#include <malloc.h>  
  
class CList  
{  
public:  
   CList(int)  
   {  
      throw "Fail!";  
   }  
};  
  
void* operator new(size_t size, char* pszFilename, int nLine)  
{  
   return malloc(size);  
}  
  
int main(void)  
{  
   try  
   {  
      // This will call ::operator new(unsigned int) to allocate heap  
      // memory. Heap memory pointed to by pList1 will automatically be  
      // deallocated by a call to ::operator delete(void*) when  
      // CList::CList(int) throws an exception.  
      CList* pList1 = new CList(10);  
   }  
   catch (...)  
   {  
   }  
  
   try  
   {  
      // This will call the overloaded ::operator new(size_t, char*, int)  
      // to allocate heap memory. When CList::CList(int) throws an  
      // exception, ::operator delete(void*, char*, int) should be called  
      // to deallocate the memory pointed to by pList2. Since  
      // ::operator delete(void*, char*, int) has not been implemented,  
      // memory will be leaked when the deallocation cannot occur.  
      CList* pList2 = new(__FILE__, __LINE__) CList(20);   // C4291  
   }  
   catch (...)  
   {  
   }  
}  
```  
  
 Im obigen Beispiel wird die Warnung C4291 generiert, da keine Positionierungsform des Operators **löschen** definiert wurde, entspricht das Format für die Platzierung des Operators **neue**. Um das Problem zu beheben, fügen Sie den folgenden Code oberhalb **main**. Beachten Sie, dass alle überladenen Operators **löschen** Funktionsparameter übereinstimmend zu jener der überladene Operator **neue**, mit Ausnahme der erste Parameter.  
  
```  
void operator delete(void* pMem, char* pszFilename, int nLine)  
{  
   free(pMem);  
}  
```