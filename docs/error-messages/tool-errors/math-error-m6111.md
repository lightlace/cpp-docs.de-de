---
title: "Mathematischer Fehler M6111 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "M6111"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6111"
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Mathematischer Fehler M6111
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stapelunterlauf  
  
 Eine Gleitkommaoperation hat einen Stapelunterlauf des 8087\/287\/387\-Coprozessors oder des Emulators zur Folge.  
  
 Dieser Fehler wird oft durch einen Aufruf einer `long double`\-Funktion ausgelöst, die keinen Wert zurückgibt.  Im folgenden Beispiel wird dieser Fehler generiert, nachdem der Code kompiliert und ausgeführt wurde:  
  
```  
long double ld() {};  
main ()  
{  
  ld();  
}  
```  
  
 Das Programm wird mit Exitcode 139 beendet.