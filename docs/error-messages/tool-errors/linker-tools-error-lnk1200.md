---
title: Linkertoolfehler LNK1200
ms.date: 11/04/2016
f1_keywords:
- LNK1200
helpviewer_keywords:
- LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
ms.openlocfilehash: c99b25a83836f1ee0bc6ba622e42ea382c377172
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466832"
---
# <a name="linker-tools-error-lnk1200"></a>Linkertoolfehler LNK1200

Fehler beim Lesen der Programmdatenbank 'Dateiname'

Die Programmdatenbank (PDB) konnte nicht gelesen werden.

Dieser Fehler kann durch eine beschädigte Datei verursacht werden.

Wenn `filename` ist die PDB-Datei für eine Objektdatei, kompilieren Sie erneut das Objekt mit ["/ Zi"](../../build/reference/z7-zi-zi-debug-information-format.md).

Wenn `filename` ist die PDB-Datei für die Hauptausgabe-Datei, und dieser Fehler ist aufgetreten, während der inkrementellen verknüpfen, die PDB-Datei und anschließend löschen.