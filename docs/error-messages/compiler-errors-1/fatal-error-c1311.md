---
title: Schwerwiegender Fehler C1311 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1311
dev_langs:
- C++
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53b3759a5fec4b072f9a9b300670d61cb0d101c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33226674"
---
# <a name="fatal-error-c1311"></a>Schwerwiegender Fehler C1311
COFF-Format kann "Var" mit der Nummer Byte(s) einer Adresse nicht statisch initialisieren  
  
 Eine Adresse, deren Wert zur Kompilierzeit nicht bekannt ist, kann statisch einer Variablen zugewiesen werden, dessen Typ Speicher von weniger als vier Bytes enthält.  
  
 Dieser Fehler kann auftreten, Code, der andernfalls ist C++-gültig.  
  
 Das folgende Beispiel zeigt eine Bedingung, die C1311 verursachen können.  
  
```  
char c = (char)"Hello, world";   // C1311  
char *d = (char*)"Hello, world";   // OK  
```