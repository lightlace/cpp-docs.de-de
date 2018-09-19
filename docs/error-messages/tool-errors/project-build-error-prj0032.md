---
title: Projektbuildfehler prj0032 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0032
dev_langs:
- C++
helpviewer_keywords:
- PRJ0032
ms.assetid: bc6acbea-4041-4237-8b5a-f0434705d89f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 106b1c3f470bbdb134a5fd53ebaef65a4392fd4b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053571"
---
# <a name="project-build-error-prj0032"></a>Projektbuildfehler PRJ0032

Die 'Outputs'-Eigenschaft für den benutzerdefinierten Buildschritt auf Projektebene enthalten "Makros", die als "Macro_expansion" ausgewertet wird.

Ein benutzerdefinierten Buildschritt an einem Projekt musste ungültige Ausgabe wahrscheinlich aufgrund eines Problems der Makro-Evaluierung. Dass der Pfad enthält Zeichen oder eine Kombination von Zeichen, die in einem Dateipfad unzulässig sind falsch formatiert wurde, wird von dieser Fehler auch bedeuten.

Um diesen Fehler zu beheben, korrigieren Sie das Makro oder die Pfadangabe. Der ausgewertete Pfad ist ein absoluter Pfad vom Projektverzeichnis.