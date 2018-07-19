---
title: Ausdrucksauswertungsfehler CXX0065 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0065
dev_langs:
- C++
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78c25c9c6bde27219f10e4047dc7a6ab416f55d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33297536"
---
# <a name="expression-evaluator-error-cxx0065"></a>Ausdrucksauswertungsfehler CXX0065
Variable erfordert Stapelrahmen  
  
 Ein Ausdruck enthält eine Variable, die im aktuellen Gültigkeitsbereich vorhanden ist, aber noch nicht erstellt wurde.  
  
 Dieser Fehler kann auftreten, wenn Sie eine Funktion, aber noch nicht Einrichten des Stapelrahmens für die Funktion der Prolog gewechselt sind oder wenn Sie in der Exitcode für die Funktion in Einzelschritten haben.  
  
 Durchlaufen der Prologcode aus, bis der Stapelrahmen eingerichtet wurde, bevor die Auswertung des Ausdrucks.  
  
 Dieser Fehler ist mit CAN0065 identisch.