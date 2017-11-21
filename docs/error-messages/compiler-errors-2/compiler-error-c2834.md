---
title: Compilerfehler C2834 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2834
dev_langs: C++
helpviewer_keywords: C2834
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5b85b01fa832b0d14d01b6b7cbb5ef65107177ef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2834"></a>Compilerfehler C2834
'Operator Operator' muss Global qualifiziert werden.  
  
 Die `new` und `delete` Operatoren sind befinden, in dem sie der Klasse gebunden. Bereichsauflösung kann nicht verwendet werden, zum Auswählen einer Version von `new` oder `delete` von einer anderen Klasse. Um mehrere Formen eines implementieren die `new` oder `delete` -Operator, erstellen Sie eine Version des Operators mit zusätzlichen formalen Parametern.