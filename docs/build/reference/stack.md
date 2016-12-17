---
title: "/STACK"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "/stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/STACK (editbin-Option)"
  - "STACK (editbin-Option)"
  - "-STACK (editbin-Option)"
  - "Stapel, Festlegen der Größe"
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# /STACK
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/STACK:reserve[,commit]  
```  
  
## Hinweise  
 Durch diese Option wird die Stapelgröße in Bytes festgelegt, wobei die Argumente dezimal oder in C\-Notation angegeben werden können.  Die **\/STACK**\-Option kann nur auf eine ausführbare Datei angewendet werden.  
  
 Das *reserve*\-Argument gibt die gesamte Stapelreservierung im virtuellen Speicher an.  EDITBIN rundet den angegebenen Wert auf die nächsten 4 Bytes auf.  
  
 Wie das optionale `commit`\-Argument interpretiert wird, hängt vom jeweiligen Betriebssystem ab.  Unter Windows NT, Windows 95 und Windows 98 wird mit `commit` die Menge des physischen Arbeitsspeichers bezeichnet, der jeweils belegt werden soll.  Die Zusicherung von virtuellem Speicher bewirkt die Belegung von Speicher in der Auslagerungsdatei.  Ein höherer `commit`\-Wert spart Zeit, wenn die Anwendung mehr Stapelspeicher benötigt, erhöht aber auch den Arbeitsspeicherbedarf und möglicherweise die Ladezeit.  
  
## Siehe auch  
 [EDITBIN\-Optionen](../../build/reference/editbin-options.md)