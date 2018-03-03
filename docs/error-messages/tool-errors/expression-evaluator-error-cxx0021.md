---
title: Ausdrucksauswertungsfehler CXX0021 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0021
dev_langs:
- C++
helpviewer_keywords:
- CXX0021
- CAN0021
ms.assetid: d6c0c35a-16c2-42c0-a7d2-e910350a47f0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 475074acf4a01c60fc1108910d5eb41c54b48923
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0021"></a>Ausdrucksauswertungsfehler CXX0021
Struktur oder Union als Skalarwert verwendet  
  
 Eine Struktur oder Union wurde in einem Ausdruck verwendet, aber es wurde kein Element angegeben.  
  
 Wenn eine Struktur oder union-Variable zu bearbeiten, kann der Name der Variablen alleine ohne Feldqualifizierer angezeigt. Wenn eine Struktur oder Union in einem Ausdruck verwendet wird, muss er durch ein bestimmtes Element gewünscht qualifiziert werden.  
  
 Geben Sie das Element, dessen Wert im Ausdruck verwendet wird.  
  
 Dieser Fehler ist mit CAN0021 identisch.