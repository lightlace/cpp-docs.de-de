---
title: Compilerfehler C2316 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2316
dev_langs: C++
helpviewer_keywords: C2316
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aed0e39ccfd320da6e6078f58a390a03e0ef08b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2316"></a>Compilerfehler C2316

> "*Ausnahme*": kann nicht aufgefangen werden, da der Destruktor und/oder den Kopierkonstruktor nicht zugegriffen werden kann  
  
Eine Ausnahme wurde durch einen Wert oder Verweis abgefangen, aber auf den copy-Konstruktor und/oder den Zuweisungsoperator konnte nicht zugegriffen werden.  
  
Dieser Code wurde von Versionen von Visual C++ vor Visual Studio 2003 akzeptiert, aber jetzt ein Fehler generiert.  
  
Konformitätsänderungen in Visual Studio 2015 vorgenommen, diese Fehler zuweisen ungültige Catch-Anweisungen von MFC-Ausnahmen abgeleitet wurde. `CException`. Da `CException` verfügt über eine geerbte privaten Kopierkonstruktor, die Klasse und die Ableitung nicht kopiert werden und nicht anhand des Werts bedeutet auch, dass sie können nicht aufgefangen werden, als Wert übergeben werden. Catch-Anweisungen, die MFC-Ausnahmen vom Wert, der zuvor geführt, die zur Laufzeit nicht abgefangene Ausnahmen abgefangen, aber der Compiler jetzt ordnungsgemäß identifiziert, diese Situation und meldet Fehler C2316. Um dieses Problem zu beheben, wird empfohlen, dass Sie die MFC-TRY/CATCH-Makros verwenden, anstatt eigene Ausnahmehandler schreiben, aber wenn dies nicht für Ihren Code geeignet ist, MFC-Ausnahmen als Verweis stattdessen abfangen.   
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2316 generiert:  
  
```  
// C2316.cpp  
// compile with: /EHsc  
#include <stdio.h>  
  
extern "C" int printf_s(const char*, ...);  
  
struct B   
{  
public:  
    B() {}  
    // Delete the following line to resolve.  
private:  
    // copy constructor  
    B(const B&)   
    {  
    }  
};  
  
void f(const B&)   
{  
}  
  
int main()   
{  
    try   
    {  
        B aB;  
        f(aB);  
    }  
    catch (B b) {   // C2316  
        printf_s("Caught an exception!\n");     
    }  
}  
```