---
title: "Compilerwarnung (Stufe 1) C4010 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4010"
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Einzeiliger Kommentar enthält Zeilenfortsetzungszeichen  
  
 Ein einzeiliger Kommentar, der mit \/\/ beginnt, enthält einen umgekehrten Schrägstrich \(\\\), der als Zeilenfortsetzungszeichen fungiert.  Der Compiler betrachtet die nächste Zeile als Fortsetzung und behandelt sie wie einen Kommentar.  
  
 Bei einigen syntaxgesteuerten Editoren wird die auf das Fortsetzungszeichen folgende Zeile nicht als Kommentar gekennzeichnet.  Ignorieren Sie die Syntaxfarbgebung in den Zeilen, für die diese Warnung ausgegeben wird.  
  
 Im folgenden Beispiel wird C4010 generiert:  
  
```  
// C4010.cpp  
// compile with: /WX  
int main() {  
   // the next line is also a comment because of the backslash \  
   int a = 3; // C4010  
   a++;  
}  
```