---
title: Ausdrucksauswertungsfehler CXX0024 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0024
dev_langs:
- C++
helpviewer_keywords:
- CXX0024
- CAN0024
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 50a07297ddabf269b003a1f14d967d1187fea96d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302460"
---
# <a name="expression-evaluator-error-cxx0024"></a>Ausdrucksauswertungsfehler CXX0024
Vorgang benötigt l-Wert  
  
 Ein Ausdruck, der nicht in einen l-Wert ausgewertet wird, wurde für einen Vorgang angegeben, der einen l-Wert erfordert.  
  
 Ein l-Wert (so genannt, weil es auf der linken Seite einer zuweisungsanweisung angezeigt wird) ist ein Ausdruck, der auf einen Speicherbereich verweist.  
  
 Beispielsweise `buffer[count]` gültiger l-Wert ist, da er auf einen bestimmten Speicherbereich verweist. Die logischen Vergleich `zed != 0` ist nicht gültiger l-Wert, da er auf "true" oder "false", nicht zu einer Speicheradresse ausgewertet wird.  
  
 Dieser Fehler ist mit CAN0024 identisch.