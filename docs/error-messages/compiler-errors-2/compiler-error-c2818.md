---
title: Compilerfehler C2818 | Microsoft-Dokumentation
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
ms.openlocfilehash: f692f52477c988c277f60a689dac5ce83a90acb2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112043"
---
# <a name="compiler-error-c2818"></a>Compilerfehler C2818

Anwendung des überladenen Operators "->" wird durch den Typ 'Typ'

Eine Neudefinition des dem Klassenmemberzugriffs-Operator enthält einen rekursiven `return` Anweisung. So definieren Sie um die `->` Operator bei der Rekursion, müssen Sie verschieben die rekursive Routine in eine separate Funktion des Operators aufgerufen überschreiben Funktion.