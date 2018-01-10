---
title: Ausdrucksauswertungsfehler CXX0017 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0017
dev_langs: C++
helpviewer_keywords:
- CAN0017
- CXX0017
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e769e9886168c9f19ad110c48d848a9b84ab8aac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0017"></a>Ausdrucksauswertungsfehler CXX0017
Symbol konnte nicht gefunden.  
  
 Ein Symbol, das in einem Ausdruck konnte nicht gefunden werden.  
  
 Eine mögliche Ursache dieses Fehlers ist ein Groß-/Kleinschreibung übereinstimmende Datentypen in den Symbolnamen. Da C und C++ Sprachen Groß-/Kleinschreibung beachtet werden, muss ein Symbolnamen in die genaue Groß-/Kleinschreibung eingegeben werden, in der sie in der Quelle definiert ist.  
  
 Dieser Fehler kann auftreten, wenn eine Variable umgewandelt werden, um die Variable während des Debuggens überwachen möchten. Die `typedef` deklariert einen neuen Namen für einen Typ jedoch einen neuen Typ nicht definiert. Der Debugger versuchte Typumwandlung erfordert den Namen des definierten Typs.  
  
 Dieser Fehler ist mit CAN0017 identisch.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Stellen Sie sicher, dass das Symbol an dem Punkt im Programm bereits deklariert wird, in dem sie verwendet wird.  
  
2.  Verwenden Sie zur Umwandlung von Variablen in der Debugger einen tatsächlicher Typname anstelle eines `typedef`-Namen definiert.