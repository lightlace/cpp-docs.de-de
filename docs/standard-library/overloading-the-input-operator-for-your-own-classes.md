---
title: "&#220;berladen des Operators &gt;&gt; f&#252;r eigene Klassen"
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
helpviewer_keywords: 
  - "Operator >>, Überladen für eigene Klassen"
  - "Operator >>"
  - "Operator >>, Überladen für eigene Klassen"
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
caps.latest.revision: 8
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# &#220;berladen des Operators &gt;&gt; f&#252;r eigene Klassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eingabestreams verwenden den Operator von Extraktions\- \(`>>`\) für die Standardtypen.  Sie können ähnliche Extraktionsoperatoren für eigene Typen schreiben; Der Erfolg hängt von Leerräumen genau verwenden ab.  
  
 Im Folgenden ein Beispiel eines Extraktionsoperators für die Klasse `Date`, die oben dargestellt wird:  
  
```  
istream& operator>> ( istream& is, Date& dt )  
{  
   is >> dt.mo >> dt.da >> dt.yr;  
   return is;  
}  
```  
  
## Siehe auch  
 [Eingabestreams](../standard-library/input-streams.md)