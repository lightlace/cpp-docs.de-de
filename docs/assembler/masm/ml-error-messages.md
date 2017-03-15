---
title: "ML Error Messages | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.errors.ml"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MASM (Microsoft Macro Assembler), ML error messages"
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# ML Error Messages
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Fehlermeldungen, die von MASM\-Komponenten generiert werden, lassen sich in drei Kategorien unterteilt:  
  
-   **Schwer wiegende Fehler.** Diese geben ein schweres Problem hin, das das Hilfsprogramm am Abschluss des normalen Vorgangs verhindert.  
  
-   **Nichtfatale Fehler.** Das Hilfsprogramm kann den Prozess ab.  Wenn dies der Fall ist, ist das Ergebnis nicht wahrscheinlich ist.  
  
-   **Warnungen.** Diese Nachrichten weisen Bedingungen an, die Sie beim Abrufen der Ergebnisse, die Sie bearbeiten möchten.  
  
 Alle Fehlermeldungen nehmen die folgende Form:  
  
```  
  
Utility: Filename (Line) : [Error_type} (Code): Message_text  
```  
  
 Dabei gilt:  
  
 `Utility`  
 Das Programm, das die Fehlermeldung gesendet hat.  
  
 *Dateiname*  
 Die Datei, die die ERROR\-generierende Bedingung enthält.  
  
 *Line*  
 Die ungefähre Zeile, in der der Fehlerzustand vorhanden ist.  
  
 *Error\_type*  
 Schwer wiegender Fehler, Warnung oder Fehler.  
  
 *Code*  
 Die eindeutigen 5 oder sechsstelliger Fehlercode.  
  
 `Message_text`  
 Ein Short und allgemeine Beschreibung des Fehlerzustands.  
  
## Siehe auch  
 [Microsoft Macro Assembler Reference](../../assembler/masm/microsoft-macro-assembler-reference.md)