---
title: "Compilerwarnung (Stufe 1) C4010"
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
  - "C4010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4010"
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
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