---
title: Compilerfehler Fehler C2722 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2722
dev_langs: C++
helpviewer_keywords: C2722
ms.assetid: 4cc2c7fa-cb12-4bcf-9df1-6d627ef62973
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c2db3d8ac30d51e04d425bd27e9d9d5c12e62931
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2722"></a>Compilerfehler Fehler C2722
':: Operator': Operatorbefehl unzulässig; 'Operator Operator' verwenden  
  
 Ein `operator` Anweisung Neudefinitionen `::new` oder `::delete`. Die `new` und `delete` Operatoren sind global, sodass der Bereichsauflösungsoperator (`::`) ist ohne Bedeutung. Entfernen Sie die `::` Operator.