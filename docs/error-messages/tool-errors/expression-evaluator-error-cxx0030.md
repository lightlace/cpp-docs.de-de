---
title: Ausdrucksauswertungsfehler CXX0030 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0030
dev_langs:
- C++
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 669c585c637129c1fb6a480d91b31e5a1264fd22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298115"
---
# <a name="expression-evaluator-error-cxx0030"></a>Ausdrucksauswertungsfehler CXX0030
Ausdruck kann nicht ausgewertet werden  
  
 Ausdrucksauswertung des Debuggers konnte einen Wert für den Ausdruck nicht abgerufen werden, wenn geschrieben. Eine wahrscheinliche Ursache ist, dass der Ausdruck in den Speicher verweist, die außerhalb des Programms Adressraum (dereferenzierender null-Zeiger ist ein Beispiel). Windows lässt nicht den Zugriff auf Speicher, der außerhalb des Programms Adressraum ist.  
  
 Möglicherweise möchten die Verwendung von Klammern zur Steuerung der Reihenfolge der Auswertung Ausdruck neu schreiben.  
  
 Dieser Fehler ist mit CAN0030 identisch.