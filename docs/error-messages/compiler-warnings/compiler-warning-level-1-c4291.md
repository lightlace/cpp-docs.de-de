---
title: "Compilerwarnung (Stufe 1) C4291 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4291"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4291"
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4291
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Deklaration': Kein zugehöriger Operator "delete" gefunden; Speicher wird nicht freigegeben, wenn die Initialisierung eine Ausnahme auslöst  
  
 Es wird eine [new](../../cpp/new-operator-cpp.md)\-Positionierung verwendet, für die keine [delete](../../cpp/delete-operator-cpp.md)\-Positionierung vorhanden ist.  
  
 Wenn mit dem Operator **new** Arbeitsspeicher für ein Objekt belegt wird, wird der Konstruktor des Objekts aufgerufen.  Wenn der Konstruktor eine Ausnahme auslöst, sollte die Belegung des gesamten für ein Objekt belegten Speichers aufgehoben werden.  Dies ist jedoch nur möglich, wenn für den Operator **new** der entsprechende Operator **delete** vorhanden ist.  
  
 Wenn Sie den Operator **new** ohne zusätzliche Argumente verwenden und die Kompilierung mit den Optionen [\/GX](../../build/reference/gx-enable-exception-handling.md), [\/EHs](../../build/reference/eh-exception-handling-model.md) oder **\/EHa** durchführen, um die Ausnahmebehandlung zu aktivieren, generiert der Compiler Code, durch den der Operator **delete** aufgerufen wird, sobald der Konstruktor eine Ausnahme auslöst.  
  
 Wenn Sie die Positionierungsform des Operators **new** verwenden \(ein Format, das neben der Belegungsgröße auch Argumente enthält\) und der Konstruktor des Objekts eine Ausnahme auslöst, generiert der Compiler nach wie vor Code zum Aufrufen des Operators **delete**. Dies ist jedoch nur der Fall, wenn eine Positionierungsform des Operators **delete** vorhanden ist, die der Positionierungsform des Operators **new** entspricht, durch den Arbeitsspeicher belegt wurde.  Beispiel:  
  
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
  
 Durch das vorangehende Beispiel wird die Warnung C4291 generiert, da keine Positionierungsform des Operators **delete** definiert wurde, die mit der Positionierungsform des Operators **new** übereinstimmt.  Um das Problem zu beheben, fügen Sie folgenden Code oberhalb von **main** ein.  Beachten Sie, dass alle Funktionsparameter des überladenen Operators **delete** – mit Ausnahme des ersten Parameters – mit denen des überladenen Operators **new** übereinstimmen.  
  
```  
void operator delete(void* pMem, char* pszFilename, int nLine)  
{  
   free(pMem);  
}  
```