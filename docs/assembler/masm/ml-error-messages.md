---
title: ML-Fehlermeldungen
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- vc.errors.ml
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
ms.openlocfilehash: 1b065433a1a6baf9bf2631aeb2f53421f8efb83b
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75312624"
---
# <a name="ml-error-messages"></a>ML-Fehlermeldungen

Die von MASM-Komponenten generierten Fehlermeldungen werden in drei Kategorien unterteilt:

- **Schwerwiegende Fehler.** Diese weisen auf ein schwerwiegendes Problem hin, das verhindert, dass das Hilfsprogramm den normalen Prozess abgeschlossen.

- **Nicht schwerwiegende Fehler.** Das Hilfsprogramm kann seinen Prozess vervollständigen. Wenn dies der Fall ist, ist das Ergebnis wahrscheinlich nicht das gewünschte Ergebnis.

- **Hinweise.** Diese Meldungen weisen auf Bedingungen hin, die möglicherweise verhindern, dass Sie die gewünschten Ergebnisse erhalten.

Alle Fehlermeldungen gehen wie folgt vor:

> *Hilfsprogramm*: *Dateiname* (*Zeile*): {*Error_type*} (*Code*): *Message_text*

Dabei gilt:

*Dienstprogramm*\
Das Programm, das die Fehlermeldung gesendet hat.

*Dateiname*\
Die Datei, die die Fehler Generierungs Bedingung enthält.

*Zeilen*\
Die ungefähre Zeile, in der der Fehlerzustand vorhanden ist.

*Error_type*\
Schwerwiegender Fehler, Fehler oder Warnung.

*Code*\
Der eindeutige, 5-oder 6-stellige Fehlercode.

*Message_text*\
Eine kurze und allgemeine Beschreibung des Fehler Zustands.

## <a name="see-also"></a>Siehe auch

[Microsoft Macro Assembler-Referenz](microsoft-macro-assembler-reference.md)
