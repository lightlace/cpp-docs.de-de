---
title: ML-Fehlermeldungen
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- vc.errors.ml
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
ms.openlocfilehash: aa0440afae980e218c32ab3296bd7c6fb2b444d9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62202210"
---
# <a name="ml-error-messages"></a>ML-Fehlermeldungen

Die Fehlermeldungen, die von MASM-Komponenten generiert werden, fallen in drei Kategorien:

- **Schwerwiegender Fehler.** Diese weisen ein schwerwiegendes Problem, das verhindert, dass das Hilfsprogramm die normalen Prozess.

- **Nicht schwerwiegende Fehler.** Das Hilfsprogramm kann der Prozess abgeschlossen werden. Wenn dies der Fall, wird das Ergebnis wahrscheinlich nicht auf die gewünschte.

- **Warnungen.** Diese Meldungen zeigen die Bedingungen, die verhindern, können Sie die gewünschten Ergebnisse an.

Alle Fehlermeldungen führen Sie das folgende Format:

> *Utility*: *FileName* (*Zeile*): {*Error_type*} (*Code*): *Message_text*

Dabei gilt:

*Hilfsprogramm*<br/>
Die Anwendung, die die Fehlermeldung gesendet.

*Filename*<br/>
Die Datei, die den Fehler generiert Bedingung enthält.

*Line*<br/>
Die ungefähre Zeile, in denen die fehlerbedingung vorhanden ist.

*Error_type*<br/>
Schwerwiegender Fehler, Fehler oder Warnung.

*Code*<br/>
Der Fehlercode für die eindeutige 5 oder 6 Ziffern.

*Message_text*<br/>
Eine kurze und allgemeine Beschreibung des Fehlerzustands.

## <a name="see-also"></a>Siehe auch

[Referenz zum Microsoft-Makroassembler](../../assembler/masm/microsoft-macro-assembler-reference.md)<br/>