---
title: "Compilerwarnung (Stufe 1) C4716 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4716"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4716"
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 1) C4716
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion' muss einen Wert zurückgeben  
  
 Die angegebene Funktion hat keinen Wert zurückgegeben.  
  
 Nur Funktionen mit dem Rückgabetyp void können den Rückgabebefehl ohne entsprechenden Rückgabewert verwenden.  
  
 Beim Aufrufen dieser Funktion wird ein nicht definierter Wert zurückgegeben.  
  
 Diese Warnung wird automatisch zu einem Fehler heraufgestuft.  Um dieses Verhalten zu ändern, verwenden Sie [\#pragma warning](../../preprocessor/warning.md).  
  
 Im folgenden Beispiel wird C4716 generiert:  
  
```  
// C4716.cpp  
// compile with: /c /W1  
// C4716 expected  
#pragma warning(default:4716)  
int test() {  
   // uncomment the following line to resolve  
   // return 0;  
}  
```