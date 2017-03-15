---
title: "Compilerwarnung C4394 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4394"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4394"
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerwarnung C4394
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Ein anwendungsdomänenspezifisches Symbol sollte nicht mit \_\_declspec\(dllexport\) markiert werden  
  
 Eine mit dem [appdomain](../../cpp/appdomain.md) `__declspec`\-Modifizierer markierte Funktion wird zu MSIL kompiliert \(nicht zu systemeigen\), und Exporttabellen \([export](../../windows/export.md) `__declspec`\-Modifizierer\) werden für verwaltete Funktion nicht unterstützt.  
  
 Sie können eine verwaltete Funktion mit öffentlicher Zugriffsmöglichkeit deklarieren.  Weitere Informationen finden Sie unter [Typsichtbarkeit](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) und [Membersichtbarkeit](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility).  
  
 C4394 wird immer als Fehler ausgegeben.  Sie können diese Warnung mit `#pragma warning` oder **\/wd** deaktivieren. Weitere Informationen finden Sie unter [warning](../../preprocessor/warning.md) oder [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won \(Warnstufe\)](../../build/reference/compiler-option-warning-level.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4394 generiert.  
  
```  
// C4394.cpp  
// compile with: /clr /c  
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394  
__declspec(dllexport) int g2 = 0;   // OK  
```