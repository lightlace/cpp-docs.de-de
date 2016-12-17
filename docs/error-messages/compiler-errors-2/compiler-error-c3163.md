---
title: "Compilerfehler C3163"
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
  - "C3163"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3163"
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3163
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Konstrukt': Attribute stimmen nicht mit vorheriger Deklaration überein  
  
 Die für eine Definition angegebenen Attribute stimmen nicht mit den Attributen einer Deklaration überein.  
  
 Eine Möglichkeit zum Beheben des Fehlers C3163 besteht darin, Attribute in der Vorwärtsdeklaration zu entfernen.  Die Anzahl von Attributen in einer Vorwärtsdeklaration muss kleiner oder zumindest gleich der Attributanzahl in der Definition sein.  
  
 Eine mögliche Ursache des Fehlers C3163 ist die Source Code Annotation Language von Microsoft \(SAL\).  Die SAL\-Makros werden nur erweitert, wenn Sie das Projekt mit dem **\/analyze**\-Kennzeichen kompilieren.  Bei einem Programm, das problemlos ohne "\/analyze" kompiliert wird, kann der Fehler C3163 ausgelöst werden, wenn Sie versuchen, es mit der \/analyze\-Option erneut zu kompilieren.  Weitere Informationen über SAL finden Sie unter [SAL\-Anmerkungen](../../c-runtime-library/sal-annotations.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3163 generiert.  
  
```  
// C3163.cpp  
// compile with: /clr /c  
using namespace System;  
  
[CLSCompliant(true)] void f();  
[CLSCompliant(false)] void f() {}   // C3163  
// try the following line instead  
// [CLSCompliant(true)] void f() {}  
```  
  
## Siehe auch  
 [SAL\-Anmerkungen](../../c-runtime-library/sal-annotations.md)