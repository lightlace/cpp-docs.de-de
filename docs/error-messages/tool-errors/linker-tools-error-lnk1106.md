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
ms.openlocfilehash: ce6a8b2ef9ac807e48cff42186453666cebda5ee
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055983"
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