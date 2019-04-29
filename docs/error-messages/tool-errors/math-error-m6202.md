---
title: Mathematischer Fehler M6202
ms.date: 11/04/2016
f1_keywords:
- M6202
helpviewer_keywords:
- M6202
ms.assetid: 4d17045f-c6dc-4705-9512-e9af12c35fb4
ms.openlocfilehash: c216c4d01513868dd56f47c7d5ca7f8b734d1797
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393232"
---
# <a name="math-error-m6202"></a>Mathematischer Fehler M6202

'Funktion': -Fehler

Ein Argument für die angegebene Funktion wurde ein Singularitätswert für diese Funktion. Die Funktion ist für dieses Argument nicht definiert.

Dieser Fehler führt zum Aufruf der `_matherr` -Funktion mit den Namen der Funktion, die Argumente und den Fehlertyp. Sie können Umschreiben der `_matherr` Funktion, um die Behandlung bestimmter Gleitkommaoperationen Laufzeit anpassen.