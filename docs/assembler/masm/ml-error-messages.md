---
title: ML-Fehlermeldungen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- vc.errors.ml
dev_langs:
- C++
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fbc2ae6388ad11a411850d03de421d2f6820fc03
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057096"
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