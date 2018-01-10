---
title: ML-Fehlermeldungen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.errors.ml
dev_langs: C++
helpviewer_keywords: MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1fa5933c9c676b76ebe342ffa848e7b40926da08
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ml-error-messages"></a>ML-Fehlermeldungen
MASM-Komponenten generierten Fehlermeldungen werden in drei Kategorien eingeteilt:  
  
-   **Schwerwiegender Fehler.** Diese Werte zeigen ein schwerwiegendes Problem aufgetreten, das verhindert, dass das Hilfsprogramm die normalen Prozess ausführen.  
  
-   **Nicht schwerwiegende Fehler.** Das Hilfsprogramm kann seine abzuschließen. Wenn dies der Fall ist, wird das Ergebnis wahrscheinlich nicht auf die gewünschte.  
  
-   **Warnungen.** Diese Meldungen geben Bedingungen an, die verhindern, können Sie die gewünschten Ergebnisse abrufen.  
  
 Alle Fehlermeldungen weisen das folgende Format:  
  
```  
  
Utility: Filename (Line) : [Error_type} (Code): Message_text  
```  
  
 Dabei gilt:  
  
 `Utility`  
 Das Programm, das die Fehlermeldung gesendet.  
  
 *Filename*  
 Die Datei, die den Fehler generiert Bedingung enthält.  
  
 *Line*  
 Die ungefähre Zeile, in dem die fehlerbedingung vorhanden ist.  
  
 *Error_type*  
 Schwerwiegender Fehler, Fehler oder Warnung.  
  
 *Code*  
 Der Fehlercode für den eindeutigen 5 oder 6 Ziffern.  
  
 `Message_text`  
 Eine kurze und allgemeine Beschreibung des Fehlerzustands.  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz zum Microsoft-Makroassembler](../../assembler/masm/microsoft-macro-assembler-reference.md)