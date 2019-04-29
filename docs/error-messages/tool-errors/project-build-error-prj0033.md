---
title: Projektbuildfehler PRJ0033
ms.date: 11/04/2016
f1_keywords:
- PRJ0033
helpviewer_keywords:
- PRJ0033
ms.assetid: 84d4a052-0586-4b78-9315-81c1e8386c1e
ms.openlocfilehash: e074ee18508271b56686aa16f9012085ed3bd77d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62346920"
---
# <a name="project-build-error-prj0033"></a>Projektbuildfehler PRJ0033

Die 'Additional Dependencies'-Eigenschaft für den benutzerdefinierten Build Schritt für die Datei "Datei" enthalten "Makro" das ausgewertet wird zu "Macro_expansion".

Ein benutzerdefinierten Buildschritt auf eine Datei enthielt einen Fehler in seiner zusätzliche Abhängigkeit wahrscheinlich aufgrund eines Problems der Makro-Evaluierung. Dass der Pfad enthält Zeichen oder eine Kombination von Zeichen, die in einem Dateipfad unzulässig sind falsch formatiert wurde, wird von dieser Fehler auch bedeuten.

Um diesen Fehler zu beheben, korrigieren Sie das Makro oder die Pfadangabe. Der ausgewertete Pfad ist ein absoluter Pfad vom Projektverzeichnis.