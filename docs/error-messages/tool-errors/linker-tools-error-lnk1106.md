---
title: Linkertoolfehler Lnk1106 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1106
dev_langs:
- C++
helpviewer_keywords:
- LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 719ff1a87f3f1afc19cf38736c0059c46a8a9bdc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110873"
---
# <a name="linker-tools-error-lnk1106"></a>Linkertoolfehler LNK1106

Ungültige Datei oder der Datenträger ist voll: kann nicht nach Position suchen

Das Tool konnte nicht lesen oder Schreiben in `location` in eine Datei mit zugewiesenem Speicher.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Der Datenträger ist voll.

     Geben Sie Speicherplatz frei, und erneut auf den link.

1. Versucht, über ein Netzwerk zu verknüpfen.

     Manche Netzwerke unterstützen nicht vollständig die Speicherabbilddateien, die vom Linker verwendet werden. Versuchen Sie, eine Verknüpfung auf dem lokalen Datenträger.

1. Ungültige Block auf dem Datenträger.

     Obwohl das Betriebssystem und Datenträgerhardware solcher Fehler erkannt haben sollen, empfiehlt es sich zum Ausführen von Programmen datenträgerüberprüfung.

1. Kein weiterer Heapspeicher verfügbar.

     Finden Sie unter [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) für Weitere Informationen.