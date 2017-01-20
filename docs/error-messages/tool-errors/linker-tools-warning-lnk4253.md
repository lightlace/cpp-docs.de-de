---
title: "Linkertoolwarnung LNK4253"
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
  - "LNK4253"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4253"
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolwarnung LNK4253
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Abschnitt 'Abschnitt1' wurde nicht mit 'Abschnitt2' zusammengeführt; bereits mit 'Abschnitt3' zusammengeführt  
  
 Mehrere in Konflikt stehende Zusammenführungsanforderungen wurden vom Linker erkannt.  Eine der Anforderungen wird vom Linker ignoriert.  
  
 Eine **\/MERGE**\-Option oder Direktive wurde gefunden, und der Abschnitt `from` wurde bereits mit einem anderen Abschnitt aufgrund einer vorherigen **\/MERGE**\-Option oder \-Direktive zusammengeführt \(oder aufgrund einer impliziten Zusammenführung des Linkers\).  
  
 Zur Behebung der Warnmeldung LNK4253 entfernen Sie eine der Zusammenführungsanforderungen.  
  
 Bei x86\-Computern und Windows CE\-Plattformen \(ARM, MIPS, SH4 und Thumb\) mit Visual C\+\+ ist der .CRT\-Abschnitt schreibgeschützt.  Wenn der Code auf dem vorherigen Verhalten \(.CRT\-Abschnitte mit Lese\-\/Schreibzugriff\) beruht, kann dies zu unerwartetem Verhalten führen.  
  
 Weitere Informationen finden Sie unter  
  
-   [\/MERGE \(Abschnitte kombinieren\)](../../build/reference/merge-combine-sections.md)  
  
-   [Kommentar](../../preprocessor/comment-c-cpp.md)  
  
## Beispiel  
 Im folgenden Beispiel wird der Linker angewiesen, den Abschnitt `.rdata` zweimal zusammenzuführen, jedoch mit verschiedenen Abschnitten.  Im folgenden Beispiel wird LNK4253 generiert.  
  
```  
// LNK4253.cpp  
// compile with: /W1 /link /merge:.rdata=text2  
// LNK4253 expected  
#pragma comment(linker, "/merge:.rdata=.text")  
int main() {}  
```