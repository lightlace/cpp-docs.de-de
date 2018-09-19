---
title: Linkertoolfehler Lnk1201 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1201
dev_langs:
- C++
helpviewer_keywords:
- LNK1201
ms.assetid: 64c3f496-a428-4b54-981e-faa82ef9c8a1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c133748f95846160e1387e31e023d9ce459b281
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055261"
---
# <a name="linker-tools-error-lnk1201"></a>Linkertoolfehler LNK1201

Fehler beim Schreiben in die Programmdatenbank 'Dateiname'; nicht genügend Speicherplatz, Ungültiger Pfad oder keine ausreichenden Berechtigungen überprüfen

LINK konnte nicht in die Programmdatenbank (PDB) für die Ausgabedatei schreiben.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Die Datei ist beschädigt. Löschen Sie die PDB-Datei und anschließend.

1. Nicht genügend Speicherplatz zum Schreiben der Datei.

1. Laufwerk ist nicht verfügbar ist, möglicherweise aufgrund eines Netzwerkproblems.

1. Der Debugger ist auf die Anwendung, die Sie verknüpfen möchten.

1. Kein weiterer Heapspeicher verfügbar.  Finden Sie unter [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) für Weitere Informationen.