---
title: 1.4-Kompatibilität | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 662ad260-b9a1-43b7-b269-ef6ff0714e05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a332d8fb5de172c363c6f9c1bebba65d6fa0ff8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381815"
---
# <a name="14-compliance"></a>1.4 Kompatibilität

Eine Implementierung der OpenMP-C-/C++-API ist *OpenMP-kompatible* Wenn es erkennt und behält die Semantik der alle Elemente dieser Spezifikation ist, wie in Kapitel 1, 2, 3, 4, angeordnet und Anhang C. Anhänge A, B, D, E und F für Informationen nur zu Evaluierungszwecken nutzen und sind nicht Teil der Spezifikation. Implementierungen, die nur eine Teilmenge der API enthalten sind nicht in der OpenMP-kompatibel.

Das OpenMP-C- und C++-API ist eine Erweiterung für die Basissprache, die durch eine Implementierung unterstützt wird. Wenn die Basissprache nicht unterstützt wird ein Sprachkonstrukt oder eine Erweiterung, die angezeigt wird in diesem Dokument, wird die Implementierung der OpenMP ist nicht erforderlich, um es zu unterstützen.

Alle standardmäßigen C- und C++-Bibliotheksfunktionen und integrierte Funktionen (d. h. Funktionen, die von denen der Compiler verfügt über spezifische Kenntnisse) muss threadsicher sein. Nicht synchronisierte Verwenden von threadsichere Funktionen, wenn unterschiedliche Threads innerhalb eines parallelen Bereichs ergibt keinen nicht definiertem Verhalten. Allerdings kann das Verhalten sein keiner seriellen Region identisch. (Eine zufällige Zahl Generierungsfunktion ist ein Beispiel.)

OpenMP C-/C++-API gibt an, dass bestimmte Verhalten *Implementierung definiert.* Keine entsprechende Implementierung von OpenMP ist erforderlich, um zu definieren und Dokumentieren Sie das Verhalten in diesen Fällen. Finden Sie unter [Anhang E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md), Seite 97, eine Liste der die Implementierung definiertes Verhalten.