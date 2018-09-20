---
title: 2.7 Datenumgebung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 74e44b3c-e18c-4773-8e78-cd6c4413ae57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 17c60c621defa15c034f57d0af8f14637db54f03
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378136"
---
# <a name="27-data-environment"></a>2.7 Datenumgebung

In diesem Abschnitt wird eine Richtlinie und mehrere Klauseln zum Steuern der datenumgebung während der Ausführung von parallelen Bereichen wie folgt:

- Ein **Threadprivate** Richtlinie (siehe folgenden Abschnitt) wird bereitgestellt werden, um für einen Thread Dateigültigkeitsbereichs-, -Namespace-Gültigkeitsbereich oder Blockbereiche mit statischen Variablen lokalen machen.

- Klauseln, die auf die Direktiven zum Steuern der Freigabe Attribute von Variablen für die Dauer der parallelen oder Freigabe von Arbeit Konstrukte angegeben werden können, werden in beschrieben [Abschnitt 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite 25.