---
title: Linkertoolfehler Lnk1200 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1200
dev_langs:
- C++
helpviewer_keywords:
- LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03ecd51142bf30230b6b177a36e007345e93bf2c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059315"
---
# <a name="linker-tools-error-lnk1200"></a>Linkertoolfehler LNK1200

Fehler beim Lesen der Programmdatenbank 'Dateiname'

Die Programmdatenbank (PDB) konnte nicht gelesen werden.

Dieser Fehler kann durch eine beschädigte Datei verursacht werden.

Wenn `filename` ist die PDB-Datei für eine Objektdatei, kompilieren Sie erneut das Objekt mit ["/ Zi"](../../build/reference/z7-zi-zi-debug-information-format.md).

Wenn `filename` ist die PDB-Datei für die Hauptausgabe-Datei, und dieser Fehler ist aufgetreten, während der inkrementellen verknüpfen, die PDB-Datei und anschließend löschen.