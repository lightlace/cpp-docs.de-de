---
title: 2.7 Datenumgebung
ms.date: 11/04/2016
ms.assetid: 74e44b3c-e18c-4773-8e78-cd6c4413ae57
ms.openlocfilehash: b65dfc7d7694b36ef4f89351579cd73e07ab537c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491966"
---
# <a name="27-data-environment"></a>2.7 Datenumgebung

In diesem Abschnitt wird eine Richtlinie und mehrere Klauseln zum Steuern der datenumgebung während der Ausführung von parallelen Bereichen wie folgt:

- Ein **Threadprivate** Richtlinie (siehe folgenden Abschnitt) wird bereitgestellt werden, um für einen Thread Dateigültigkeitsbereichs-, -Namespace-Gültigkeitsbereich oder Blockbereiche mit statischen Variablen lokalen machen.

- Klauseln, die auf die Direktiven zum Steuern der Freigabe Attribute von Variablen für die Dauer der parallelen oder Freigabe von Arbeit Konstrukte angegeben werden können, werden in beschrieben [Abschnitt 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite 25.