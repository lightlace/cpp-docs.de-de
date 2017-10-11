---
title: Compilerfehler C2818 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2818
dev_langs:
- C++
helpviewer_keywords:
- C2818
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 02c1b8e67679e7b8ce69b202c3ddef899439095d
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2818"></a>Compilerfehler C2818
Anwendung von überladenen 'Operator ->"wird durch den Typ 'Typ'  
  
 Eine Neudefinition des dem Klassenmemberzugriffs-Operator enthält einen rekursiven `return` Anweisung. Neudefinieren der `->` -Operator mit Rekursion, müssen Sie verschieben Funktion zum Überschreiben der rekursive Routine an eine separate Funktion, die von der Operator aufgerufen.
