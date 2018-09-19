---
title: Linkertoolfehler Lnk2013 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2013
dev_langs:
- C++
helpviewer_keywords:
- LNK2013
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d04ce4ca8079317da090cf05d43f41e4e40a6b19
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041739"
---
# <a name="linker-tools-error-lnk2013"></a>Linkertoolfehler LNK2013

Fixup-Typ Fixup-Überlauf. Ziel 'Symbolname' ist außerhalb des Bereichs

Der Linker kann die erforderliche Adresse bzw. den Offset in die angegebene Anweisung nicht finden, da die Entfernung zwischen Zielsymbol und Anweisung zu groß ist.

Sie können dieses Problem zu beheben, durch die Erstellung mehrerer Abbilder oder mithilfe der [/ORDER](../../build/reference/order-put-functions-in-order.md) option aus, damit die Anweisung und das Ziel näher beieinander.

Wenn der Symbolname ein benutzerdefiniertes (und kein vom Compiler generiertes) Symbol ist, können Sie auch versuchen, den Fehler mithilfe der folgenden Maßnahmen zu beheben:

- Ändern Sie die statische Funktion in eine nicht statische Funktion.

- Benennen Sie den Codeabschnitt mit der statischen Funktion um, sodass er dem Namen des Aufrufers entspricht.

Überprüfen Sie mit `DUMPBIN /SYMBOLS`, ob eine Funktion statisch ist.