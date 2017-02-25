---
title: "Compilerwarnung (Stufe 3) C4792 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4792"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4792"
ms.assetid: c047ce69-a622-44e1-9425-d41aa9261c61
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerwarnung (Stufe 3) C4792
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Funktion 'Funktion' wurde unter Verwendung von „sysimport“ und durch Verweis von systemeigenem Code deklariert. Eine Importbibliothek ist zum Verknüpfen erforderlich.  
  
 Eine mit „DllImport“ importierte systemeigene Funktion wurde von einer nicht verwalteten Funktion aufgerufen. Daher müssen Sie für die DLL eine Verknüpfung mit der Importbibliothek herstellen.  
  
 Diese Warnung kann nicht im Code oder durch Ändern der Kompilierungsweise aufgelöst werden. Verwenden Sie das [warning](../../preprocessor/warning.md)\-Pragma, um diese Warnung zu deaktivieren.  
  
 Im folgenden Beispiel wird C4792 generiert.  
  
```  
// C4792.cpp // compile with: /clr /W3 // C4792 expected using namespace System::Runtime::InteropServices; [DllImport("msvcrt")] extern "C" int __cdecl puts(const char *); int main() {} // Uncomment the following line to resolve. // #pragma warning(disable : 4792) #pragma unmanaged void func(void){ puts("test"); }  
```