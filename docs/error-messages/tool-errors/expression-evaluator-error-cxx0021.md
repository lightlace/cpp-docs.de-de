---
title: Ausdrucksauswertungsfehler CXX0021 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0021
dev_langs:
- C++
helpviewer_keywords:
- CXX0021
- CAN0021
ms.assetid: d6c0c35a-16c2-42c0-a7d2-e910350a47f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 996fc46982d809da5e0b37b83f2940102892167e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="expression-evaluator-error-cxx0021"></a>Ausdrucksauswertungsfehler CXX0021
Struktur oder Union als Skalarwert verwendet  
  
 Eine Struktur oder Union wurde in einem Ausdruck verwendet, aber es wurde kein Element angegeben.  
  
 Wenn eine Struktur oder union-Variable zu bearbeiten, kann der Name der Variablen alleine ohne Feldqualifizierer angezeigt. Wenn eine Struktur oder Union in einem Ausdruck verwendet wird, muss er durch ein bestimmtes Element gewünscht qualifiziert werden.  
  
 Geben Sie das Element, dessen Wert im Ausdruck verwendet wird.  
  
 Dieser Fehler ist mit CAN0021 identisch.