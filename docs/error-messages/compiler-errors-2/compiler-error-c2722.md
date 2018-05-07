---
title: Compilerfehler Fehler C2722 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2722
dev_langs:
- C++
helpviewer_keywords:
- C2722
ms.assetid: 4cc2c7fa-cb12-4bcf-9df1-6d627ef62973
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c8838ed6b2d202d58c9553a773da9653839b6c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2722"></a>Compilerfehler Fehler C2722
':: Operator': Operatorbefehl unzulässig; 'Operator Operator' verwenden  
  
 Ein `operator` Anweisung Neudefinitionen `::new` oder `::delete`. Die `new` und `delete` Operatoren sind global, sodass der Bereichsauflösungsoperator (`::`) ist ohne Bedeutung. Entfernen Sie die `::` Operator.