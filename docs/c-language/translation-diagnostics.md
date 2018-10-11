---
title: 'Übersetzung: Diagnose | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d297cfd4f4dee49d3344ae2f159f85682f05ea2f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017585"
---
# <a name="translation-diagnostics"></a>Übersetzung: Diagnose

**ANSI 2.1.1.3** Wie eine Diagnose identifiziert wird

Microsoft C erzeugt Fehlermeldungen in der Form:

> *filename* **(** *line-number* **) :** *diagnostic* **C**<em>number</em> *message*

Hierbei ist *filename* der Name der Quelldatei, in der der Fehler aufgetreten ist; *line-number* die Nummer der Zeile, in der der Compiler den Fehler festgestellt hat; *diagnostic* entweder „error“ oder „warning“; *number* eine eindeutige vierstellige Zahl (der ein **C** vorangestellt ist, wie in der Syntax kenntlich gemacht), die den Fehler bzw. die Warnung angibt, und *message* eine erläuternde Meldung.

## <a name="see-also"></a>Siehe auch

[Implementation-Defined Behavior (Durch die Implementierung definiertes Verhalten)](../c-language/implementation-defined-behavior.md)