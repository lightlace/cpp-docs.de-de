---
title: Linkertoolfehler LNK1200
ms.date: 11/04/2016
f1_keywords:
- LNK1200
helpviewer_keywords:
- LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
ms.openlocfilehash: c99b25a83836f1ee0bc6ba622e42ea382c377172
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62213549"
---
# <a name="linker-tools-error-lnk1200"></a>Linkertoolfehler LNK1200

Fehler beim Lesen der Programmdatenbank 'Dateiname'

Die Programmdatenbank (PDB) konnte nicht gelesen werden.

Dieser Fehler kann durch eine beschädigte Datei verursacht werden.

Wenn `filename` ist die PDB-Datei für eine Objektdatei, kompilieren Sie erneut das Objekt mit ["/ Zi"](../../build/reference/z7-zi-zi-debug-information-format.md).

Wenn `filename` ist die PDB-Datei für die Hauptausgabe-Datei, und dieser Fehler ist aufgetreten, während der inkrementellen verknüpfen, die PDB-Datei und anschließend löschen.