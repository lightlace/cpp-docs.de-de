---
title: "Compilerfehler C2017"
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
  - "C2017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2017"
ms.assetid: 1083eed9-9906-4a97-883c-54e52d7e82cd
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ungültige Escapesequenz  
  
 Eine Escape\-Sequenz, z. B. **\\t**, wurde außerhalb einer Zeichen\- oder Zeichenfolgenkonstante angegeben.  
  
 Im folgenden Beispiel wird C2017 generiert:  
  
```  
// C2017.cpp  
int main() {  
   char test1='a'\n;   // C2017  
   char test2='a\n';   // ok  
}  
```  
  
 C2017 kann auftreten, wenn der Operator "stringize" mit Zeichenfolgen verwendet wird, die Escape\-Sequenzen enthalten.  
  
 Im folgenden Beispiel wird C2017 generiert:  
  
```  
// C2017b.cpp  
#define TestDfn(x) AfxMessageBox(#x)  
TestDfn(CString("\\") + CString(".h\"\n\n"));   // C2017  
```