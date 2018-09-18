---
title: Mathematischer Fehler M6202 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6202
dev_langs:
- C++
helpviewer_keywords:
- M6202
ms.assetid: 4d17045f-c6dc-4705-9512-e9af12c35fb4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 328336e61c299cf9b9816ddfce7212f1798eae37
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058548"
---
# <a name="math-error-m6202"></a>Mathematischer Fehler M6202

'Funktion': -Fehler

Ein Argument für die angegebene Funktion wurde ein Singularitätswert für diese Funktion. Die Funktion ist für dieses Argument nicht definiert.

Dieser Fehler führt zum Aufruf der `_matherr` -Funktion mit den Namen der Funktion, die Argumente und den Fehlertyp. Sie können Umschreiben der `_matherr` Funktion, um die Behandlung bestimmter Gleitkommaoperationen Laufzeit anpassen.