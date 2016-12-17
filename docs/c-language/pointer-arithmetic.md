---
title: "Zeigerarithmetik"
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
  - "Arithmetischer Zeiger"
  - "Zeigerarithmetik"
ms.assetid: eb924a29-59d3-48a5-9d62-9424790730eb
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Zeigerarithmetik
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Hinzufügevorgänge im Zusammenhang mit einem Zeiger und einer ganzen Zahl geben nur dann sinnvolle Ergebnisse zurück, wenn der Zeigeroperand einen Arraymember adressiert und der Ganzzahlwert eines Offsets innerhalb der Grenzen desselben Arrays erzeugt.  Wenn der Ganzzahlwert in einen Adressoffset konvertiert wird, geht der Compiler davon aus, dass zwischen der ursprünglichen Adresse und der Adresse plus Offset nur Speicherpositionen derselben Größe liegen.  
  
 Diese Annahme gilt für Arraymember.  Definitionsgemäß ist ein Array eine Reihe von Werten desselben Typs. Seine Elemente befinden sich in zusammenhängenden Speicherbereichen.  Bei der Speicherung von Typen jeder Art \(außer Arrayelemente\) ist jedoch nicht gewährleistet, dass der Speicher mit demselben Typ von Bezeichnern gefüllt wird.  Das bedeutet, dass Leerzeichen zwischen Speicherpositionen, auch Positionen von gleichen Typ, auftreten können.  Daher sind die Ergebnisse des Hinzufügens zu den Adressen oder des Subtrahierens von Adressen aller Werte mit Ausnahme von Arrayelementen nicht definiert.  
  
 Auch wenn zwei Zeigerwerte subtrahiert werden, wird so bei der Konvertierung davon ausgegangen, dass nur Werte des gleichen Typs ohne Leerzeichen zwischen den Adressen liegen, die von den Operanden angegeben werden.  
  
## Siehe auch  
 [C\-Operatoren \(additiv\)](../c-language/c-additive-operators.md)