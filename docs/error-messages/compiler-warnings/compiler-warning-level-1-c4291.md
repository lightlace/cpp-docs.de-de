---
title: Compilerwarnung (Stufe 1) C4291
ms.date: 11/04/2016
f1_keywords:
- C4291
helpviewer_keywords:
- C4291
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
ms.openlocfilehash: e1b787e7149afe93fb50cc1e6ceaecba2e787876
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384249"
---
# <a name="compiler-warning-level-1-c4291"></a>Compilerwarnung (Stufe 1) C4291

'Declaration': kein zugehöriger Delete-Operator gefunden. Speicher wird nicht freigegeben werden, wenn die Initialisierung eine Ausnahme auslöst.

Eine Platzierung [neue](../../cpp/new-operator-cpp.md) wird verwendet, für den es keine Platzierung [löschen](../../cpp/delete-operator-cpp.md).

Wenn der Arbeitsspeicher für ein Objekt mit dem Operator zugeordnet ist **neue**, wird der Konstruktor des Objekts aufgerufen. Wenn der Konstruktor eine Ausnahme auslöst, sollte der Speicher, der für das Objekt zugewiesen wurde Zuordnung aufgehoben werden. Dies kann nicht erfolgen, wenn ein Operator **löschen** Funktion vorhanden ist, der den Operator entspricht **neue**.

Wenn Sie den Operator verwenden **neue** ohne zusätzliche Argumente und die Kompilierung mit [/GX](../../build/reference/gx-enable-exception-handling.md), [/EHs](../../build/reference/eh-exception-handling-model.md), oder die/EHa-Optionen zum Aktivieren von Ausnahmebehandlung, des Compilers generiert Code für Aufrufoperator **löschen** Wenn der Konstruktor eine Ausnahme auslöst.

Wenn Sie die Positionierungsform des verwenden die **neue** -Operator (das Formular mit Argumenten zuzüglich der Größe der Zuordnung) und den Konstruktor des Objekts eine Ausnahme auslöst, generiert der Compiler Code zum Aufrufen des Operators weiterhin**löschen**; aber es wird nur der Fall, wenn eine Positionierungsform des Operators **löschen** vorhanden ist, entspricht die Positionierungsform des Operators **neue** , die den Arbeitsspeicher zugeordnet. Zum Beispiel:

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

Im obige Beispiel wird die Warnung C4291 generiert, da keine Positionierungsform des Operators **löschen** definiert wurde, entspricht die Positionierungsform des Operators **neue**. Um das Problem zu beheben, fügen Sie den folgenden Code oberhalb **main**. Beachten Sie, dass alle überladenen Operators **löschen** Funktionsparameter entsprechen denen der überladene Operator **neue**, mit Ausnahme der erste Parameter.

```
void operator delete(void* pMem, char* pszFilename, int nLine)
{
   free(pMem);
}
```