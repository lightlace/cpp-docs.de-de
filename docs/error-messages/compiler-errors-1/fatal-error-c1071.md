---
title: "Schwerwiegender Fehler C1071 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1071"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1071"
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Schwerwiegender Fehler C1071
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unerwartetes Dateiende innerhalb eines Kommentars  
  
 Der Compiler hat beim Scannen eines Kommentars das Dateiende erreicht.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Fehlendes Abschlusszeichen für einen Kommentar \(\*\/\).  
  
2.  Fehlende Zeilenendemarke nach einem Kommentar in der letzten Zeile einer Quelldatei.  
  
 Im folgenden Beispiel wird C1071 generiert:  
  
```  
// C1071.cpp  
int main() {  
}  
  
/* this comment is fine */  
/* forgot the closing tag        // C1071  
```