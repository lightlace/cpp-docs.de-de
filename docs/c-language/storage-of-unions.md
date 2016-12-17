---
title: "Speicherung von Unions"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Speicher, Union"
  - "union-Schlüsselwort [C]"
  - "union-Schlüsselwort [C], Speicher"
ms.assetid: b33d246a-8d20-41c4-89b2-ab05f1428792
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Speicherung von Unions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Speicher, der einer Union\-Variable zugeordnet wird, ist der Speicher, der für den größten Member der Union erforderlich ist.  Wenn ein kleinerer Member gespeichert wird, kann die Union\-Variable nicht verwendeten Speicherbereich enthalten.  Alle Member werden im gleichen Speicherbereich gespeichert und beginnen an derselben Adresse.  Der gespeicherte Wert wird jedes Mal überschrieben, wenn einem anderen Member ein Wert zugewiesen wird.  Beispiel:  
  
```  
union         /* Defines a union named x */  
{  
    char *a, b;  
    float f[20];  
} x;  
```  
  
 Die Member der `x`\-Union fungieren in der Reihenfolge ihrer Deklaration als Zeiger auf einen `char`\-Wert, einen `char`\-Wert und einen Array von **float**\-Werten.  Der `x` zugeordnete Speicher ist der Speicher, der für das `f`\-Array mit 20 Elementen erforderlich ist, da `f` der längste Union\-Member ist.  Da kein Tag der Union zugeordnet ist, ist ihr Typ unbenannt oder "anonym".  
  
## Siehe auch  
 [Union\-Deklarationen](../c-language/union-declarations.md)