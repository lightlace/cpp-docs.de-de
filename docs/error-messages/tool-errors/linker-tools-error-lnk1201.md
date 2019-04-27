---
title: Linkertoolfehler LNK1201
ms.date: 11/04/2016
f1_keywords:
- LNK1201
helpviewer_keywords:
- LNK1201
ms.assetid: 64c3f496-a428-4b54-981e-faa82ef9c8a1
ms.openlocfilehash: c5cbb9a7159a976ad0f96f46462669cff7b19f26
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62213263"
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