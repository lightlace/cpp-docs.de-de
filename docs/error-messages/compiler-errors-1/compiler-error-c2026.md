---
title: "Compilerfehler C2026"
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
  - "C2026"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2026"
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2026
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zeichenfolge zu lang, Zeichen am Ende wurden entfernt  
  
 Die Zeichenfolge überschreitet die maximale Länge von 16380 Einzelbytezeichen.  
  
 Vor der Verkettung nebeneinander liegender Zeichenfolgen darf eine Zeichenfolge maximal 16380 Einzelbytezeichen lang sein.  
  
 Dieser Fehler wird außerdem von einer Unicode\-Zeichenfolge ausgelöst, die ungefähr halb so lang ist.  
  
 Durch eine wie folgt definierte Zeichenfolge wird der Fehler C2026 ausgegeben:  
  
```  
char sz[] =  
"\  
imagine a really, really \  
long string here\  
";  
```  
  
 Die Zeichenfolge kann folgendermaßen unterteilt werden:  
  
```  
char sz[] =  
"\  
imagine a really, really "  
"long string here\  
";  
```  
  
 Sehr umfangreiche Zeichenfolgenliterale \(32 KB oder mehr\) können in einer benutzerdefinierten Ressource oder externen Datei gespeichert werden.  Weitere Informationen finden Sie unter [Erstellen einer neuen benutzerdefinierten Ressource oder Datenressource](../../mfc/creating-a-new-custom-or-data-resource.md).