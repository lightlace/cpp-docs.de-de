---
title: Schwerwiegender Fehler C1061 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1061
dev_langs:
- C++
helpviewer_keywords:
- C1061
ms.assetid: 9366c0bc-96e0-4967-aa7d-4ebf098de806
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fde2d3a076b4cf78a8104fd19719bec205828c68
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225701"
---
# <a name="fatal-error-c1061"></a>Schwerwiegender Fehler C1061
Compilerlimit: Blöcke zu tief geschachtelt  
  
 Die Schachtelungstiefe für Codeblöcke überschreitet die maximale Anzahl von 128 Ebenen. Hierbei handelt es sich um einen festen Grenzwert im Compiler im 32-Bit- und 64-Bit-Toolsatz von C und C++. Alle Verhaltensweisen, durch die ein Gültigkeitsbereich oder ein Block erstellt wird, können die Anzahl der Schachtelungsebenen erhöhen. So können z. B. Namespaces, Direktiven, Präprozessorerweiterungen, Vorlagenerweiterungen, Ausnahmebehandlungen, Schleifenkonstrukte und elseif-Klauseln zur Erhöhung der vom Compiler erkannten Schachtelungsebene beitragen.  
  
 Um diesen Fehler zu beheben, müssen Sie den Code umgestalten. In jedem Fall ist tief geschachtelter Code nur schwer nachzuvollziehen. Eine Reduzierung der Schachtelungsebenen des Codes verbessert die Codequalität und vereinfacht die Verwaltung. Gliedern Sie daher tief geschachtelten Code in Funktionen auf, die in ihrem ursprünglichen Kontext aufgerufen werden. Beschränken Sie die Anzahl von Schleifen oder verketteten elseif-Klauseln innerhalb eines Blocks.