---
title: Ausdrucksauswertungsfehler CXX0065 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0065
dev_langs: C++
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: db01baa10191df50c1f319bf8320263657088d75
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0065"></a>Ausdrucksauswertungsfehler CXX0065
Variable erfordert Stapelrahmen  
  
 Ein Ausdruck enthält eine Variable, die im aktuellen Gültigkeitsbereich vorhanden ist, aber noch nicht erstellt wurde.  
  
 Dieser Fehler kann auftreten, wenn Sie eine Funktion, aber noch nicht Einrichten des Stapelrahmens für die Funktion der Prolog gewechselt sind oder wenn Sie in der Exitcode für die Funktion in Einzelschritten haben.  
  
 Durchlaufen der Prologcode aus, bis der Stapelrahmen eingerichtet wurde, bevor die Auswertung des Ausdrucks.  
  
 Dieser Fehler ist mit CAN0065 identisch.