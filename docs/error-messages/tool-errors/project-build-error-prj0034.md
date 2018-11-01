---
title: Projektbuildfehler PRJ0034
ms.date: 11/04/2016
f1_keywords:
- PRJ0034
helpviewer_keywords:
- PRJ0034
ms.assetid: 1da4a55b-231b-4476-8545-6997628fbc00
ms.openlocfilehash: 7c078a3d2aef24df9151cb10f81c1b7423809e68
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549057"
---
# <a name="project-build-error-prj0034"></a>Projektbuildfehler PRJ0034

Die 'Additional Dependencies'-Eigenschaft für das benutzerdefinierte auf Projektebene erstellen enthaltenen Schritt "Makro" als "Macro_expansion" ausgewertet wird.

Ein benutzerdefinierten Buildschritt an einem Projekt enthielt einen Fehler in seiner zusätzliche Abhängigkeit wahrscheinlich aufgrund eines Problems der Makro-Evaluierung. Dass der Pfad enthält Zeichen oder eine Kombination von Zeichen, die in einem Dateipfad unzulässig sind falsch formatiert wurde, wird von dieser Fehler auch bedeuten.

Um diesen Fehler zu beheben, korrigieren Sie das Makro oder die Pfadangabe. Der ausgewertete Pfad ist ein absoluter Pfad vom Projektverzeichnis.