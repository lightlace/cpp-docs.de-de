---
title: 1.4 Kompatibilität | Microsoft Docs
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
ms.openlocfilehash: 7c1bde41491f456ff99b0cd0d1ccc8ab98508412
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="14-compliance"></a>1.4 Kompatibilität
Eine Implementierung der OpenMP-C-/C++-API bildet *OpenMP-kompatible* wenn er erkennt und behält die Semantik der alle Elemente in dieser Spezifikation ist, wie in Kapitel 1, 2, 3, 4, angeordnet und dienen der Anhang c Anhänge A, B, D, E und F Informationen nur zu Informationszwecken und sind nicht Teil der Spezifikation. Implementierungen, die nur eine Teilmenge der API enthalten sind nicht in der OpenMP-kompatibel.  
  
 OpenMP-C- und C++-API ist eine Erweiterung der Basissprache, die von einer Implementierung unterstützt wird. Wenn die Basissprache nicht unterstützt ein Sprachkonstrukt oder eine Erweiterung, die angezeigt wird in diesem Dokument, ist die Implementierung von OpenMP nicht zu ihrer Unterstützung erforderlich.  
  
 Alle standardmäßigen C- und C++-Bibliothek-Funktionen und integrierte Funktionen (d. h. Funktionen, die von denen der Compiler verfügt über genaue Kenntnisse) muss threadsicher sein. Nicht synchronisierte Verwendung threadsichere Funktionen von anderen Threads innerhalb eines parallelen Bereichs ist nicht definiertes Verhalten nicht erzeugen. Allerdings kann das Verhalten nicht dasselbe wie bei einer seriellen Region sein. (Eine zufällige Zahl Generierungsfunktion ist ein Beispiel.)  
  
 OpenMP-C-/C++-API gibt an, dass bestimmte Verhalten *Implementierung definiert.* Eine kompatible Implementierung der OpenMP ist erforderlich zum Definieren und das Verhalten in diesen Fällen zu dokumentieren. Finden Sie unter [Anhang E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md), Seite 97, eine Liste der Implementierung definierten Verhalten.