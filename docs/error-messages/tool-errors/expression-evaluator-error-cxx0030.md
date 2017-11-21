---
title: Ausdrucksauswertungsfehler CXX0030 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0030
dev_langs: C++
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ffa1dd85419943ede6a13d61cb82924c32b5e80a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0030"></a>Ausdrucksauswertungsfehler CXX0030
Ausdruck kann nicht ausgewertet werden  
  
 Ausdrucksauswertung des Debuggers konnte einen Wert für den Ausdruck nicht abgerufen werden, wenn geschrieben. Eine wahrscheinliche Ursache ist, dass der Ausdruck in den Speicher verweist, die außerhalb des Programms Adressraum (dereferenzierender null-Zeiger ist ein Beispiel). Windows lässt nicht den Zugriff auf Speicher, der außerhalb des Programms Adressraum ist.  
  
 Möglicherweise möchten die Verwendung von Klammern zur Steuerung der Reihenfolge der Auswertung Ausdruck neu schreiben.  
  
 Dieser Fehler ist mit CAN0030 identisch.