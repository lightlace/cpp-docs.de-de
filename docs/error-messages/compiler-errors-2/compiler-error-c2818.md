---
title: Compilerfehler C2818 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2818
dev_langs:
- C++
helpviewer_keywords:
- C2818
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10d7f419d528fcd2445b82e29d92442002624909
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236052"
---
# <a name="compiler-error-c2818"></a>Compilerfehler C2818
Anwendung von überladenen 'Operator ->"wird durch den Typ 'Typ'  
  
 Eine Neudefinition des dem Klassenmemberzugriffs-Operator enthält einen rekursiven `return` Anweisung. Neudefinieren der `->` -Operator mit Rekursion, müssen Sie verschieben Funktion zum Überschreiben der rekursive Routine an eine separate Funktion, die von der Operator aufgerufen.