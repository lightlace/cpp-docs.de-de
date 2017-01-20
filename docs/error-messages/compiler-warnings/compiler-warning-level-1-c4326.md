---
title: "Compilerwarnung (Stufe 1) C4326"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4326"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4326"
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4326
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Rückgabetyp von 'Funktion' sollte 'Typ1' anstatt 'Typ2' sein  
  
 Durch eine Funktion wurde ein anderer Typ als ***Typ1*** zurückgegeben.  Bei Verwendung von [\/Za](../../build/reference/za-ze-disable-language-extensions.md) wurde durch **main** beispielsweise kein `int`\-Wert zurückgegeben.  
  
 Im folgenden Beispiel wird C4326 generiert:  
  
```  
// C4326.cpp  
// compile with: /Za /W1  
char main()  
{   // C4326 try int main  
}  
```