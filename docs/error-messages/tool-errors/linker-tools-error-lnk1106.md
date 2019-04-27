---
title: Linkertoolfehler LNK1106
ms.date: 11/04/2016
f1_keywords:
- LNK1106
helpviewer_keywords:
- LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
ms.openlocfilehash: 7551e2f3f1efc90913981feb674f48aadb9ace51
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62255318"
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