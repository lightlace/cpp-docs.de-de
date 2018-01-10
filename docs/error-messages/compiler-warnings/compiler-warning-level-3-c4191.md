---
title: Compilerwarnung (Stufe 3) C4191 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4191
dev_langs: C++
helpviewer_keywords: C4191
ms.assetid: 576d3bc6-95b7-448a-af31-5d798452df09
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4a40f5a05b4efc030cd545f2ffd27325fca86294
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4191"></a>Compilerwarnung (Stufe 3) C4191
'operator/operation': unsichere Konvertierung von 'type of expression' zu 'type required'  
  
 Verschiedene Operationen, die Funktionszeiger verwenden, werden als unsicher angesehen:  
  
-   Funktionstypen mit unterschiedlichen Aufrufkonventionen.  
  
-   Funktionstypen mit unterschiedlichen Rückgabekonventionen.  
  
-   Argument- oder Rückgabetypen mit verschiedenen Größen, Typkategorien oder Klassifikationen.  
  
-   Verschiedene Länge von Argumentlisten (in `__cdecl`nur bei der Typumwandlung von längerer zu kürzer Liste, auch wenn die kürzere 'varargs' aufweist).  
  
-   Zeiger auf Daten (außer **"void"\***) als Alias für einen Zeiger auf eine Funktion.  
  
-   Alle anderen Typunterschiede, die einen Fehler oder eine Warnung bei einem `reinterpret_cast`hervorrufen würden.  
  
 Das Aufrufen dieser Funktion über den Ergebniszeiger kann zum Absturz des Programms führen.  
  
 Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
 Im folgenden Beispiel wird C4191 generiert:  
  
```  
// C4191.cpp  
// compile with: /W3 /clr  
#pragma warning(default: 4191)  
  
void __clrcall f1() { }  
void __cdecl   f2() { }  
  
typedef void (__clrcall * fnptr1)();  
typedef void (__cdecl   * fnptr2)();  
  
int main() {  
   fnptr1 fp1 = static_cast<fnptr1>(&f1);  
   fnptr2 fp2 = (fnptr2) &f2;  
  
   fnptr1 fp3 = (fnptr1) &f2;   // C4191  
   fnptr2 fp4 = (fnptr2) &f1;   // C4191  
};  
```