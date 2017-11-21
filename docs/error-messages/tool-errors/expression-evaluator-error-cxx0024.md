---
title: Ausdrucksauswertungsfehler CXX0024 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0024
dev_langs: C++
helpviewer_keywords:
- CXX0024
- CAN0024
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 386e04d8aa1655896b77f8492d7929778edd6109
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0024"></a>Ausdrucksauswertungsfehler CXX0024
Vorgang benötigt l-Wert  
  
 Ein Ausdruck, der nicht in einen l-Wert ausgewertet wird, wurde für einen Vorgang angegeben, der einen l-Wert erfordert.  
  
 Ein l-Wert (so genannt, weil es auf der linken Seite einer zuweisungsanweisung angezeigt wird) ist ein Ausdruck, der auf einen Speicherbereich verweist.  
  
 Beispielsweise `buffer[count]` gültiger l-Wert ist, da er auf einen bestimmten Speicherbereich verweist. Die logischen Vergleich `zed != 0` ist nicht gültiger l-Wert, da er auf "true" oder "false", nicht zu einer Speicheradresse ausgewertet wird.  
  
 Dieser Fehler ist mit CAN0024 identisch.