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
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 57766a4ff0b58fdc599a7124e217892e4b28539d
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1061"></a>Schwerwiegender Fehler C1061
Compilerlimit: Blöcke zu tief geschachtelt  
  
 Die Schachtelungstiefe für Codeblöcke überschreitet die maximale Anzahl von 128 Ebenen. Hierbei handelt es sich um einen festen Grenzwert im Compiler im 32-Bit- und 64-Bit-Toolsatz von C und C++. Alle Verhaltensweisen, durch die ein Gültigkeitsbereich oder ein Block erstellt wird, können die Anzahl der Schachtelungsebenen erhöhen. So können z. B. Namespaces, Direktiven, Präprozessorerweiterungen, Vorlagenerweiterungen, Ausnahmebehandlungen, Schleifenkonstrukte und elseif-Klauseln zur Erhöhung der vom Compiler erkannten Schachtelungsebene beitragen.  
  
 Um diesen Fehler zu beheben, müssen Sie den Code umgestalten. In jedem Fall ist tief geschachtelter Code nur schwer nachzuvollziehen. Eine Reduzierung der Schachtelungsebenen des Codes verbessert die Codequalität und vereinfacht die Verwaltung. Gliedern Sie daher tief geschachtelten Code in Funktionen auf, die in ihrem ursprünglichen Kontext aufgerufen werden. Beschränken Sie die Anzahl von Schleifen oder verketteten elseif-Klauseln innerhalb eines Blocks.
