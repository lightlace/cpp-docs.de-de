---
title: Schwerwiegender Fehler C1061 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1061
dev_langs:
- C++
helpviewer_keywords:
- C1061
ms.assetid: 9366c0bc-96e0-4967-aa7d-4ebf098de806
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 81963b0fffdf1b86b56b10c0776874b37ae9daa2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1061"></a>Schwerwiegender Fehler C1061
Compilerlimit: Blöcke zu tief geschachtelt  
  
 Die Schachtelungstiefe für Codeblöcke überschreitet die maximale Anzahl von 128 Ebenen. Hierbei handelt es sich um einen festen Grenzwert im Compiler im 32-Bit- und 64-Bit-Toolsatz von C und C++. Alle Verhaltensweisen, durch die ein Gültigkeitsbereich oder ein Block erstellt wird, können die Anzahl der Schachtelungsebenen erhöhen. So können z. B. Namespaces, Direktiven, Präprozessorerweiterungen, Vorlagenerweiterungen, Ausnahmebehandlungen, Schleifenkonstrukte und elseif-Klauseln zur Erhöhung der vom Compiler erkannten Schachtelungsebene beitragen.  
  
 Um diesen Fehler zu beheben, müssen Sie den Code umgestalten. In jedem Fall ist tief geschachtelter Code nur schwer nachzuvollziehen. Eine Reduzierung der Schachtelungsebenen des Codes verbessert die Codequalität und vereinfacht die Verwaltung. Gliedern Sie daher tief geschachtelten Code in Funktionen auf, die in ihrem ursprünglichen Kontext aufgerufen werden. Beschränken Sie die Anzahl von Schleifen oder verketteten elseif-Klauseln innerhalb eines Blocks.