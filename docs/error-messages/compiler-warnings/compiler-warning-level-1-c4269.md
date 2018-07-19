---
title: Compilerwarnung (Stufe 1) C4269 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4269
dev_langs:
- C++
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e393c657e12f84d3cadfacd469e35e3472a39d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281790"
---
# <a name="compiler-warning-level-1-c4269"></a>Compilerwarnung (Stufe 1) C4269
'Bezeichner': 'const' Automatische Daten, die mit dem vom Compiler generierten Standardkonstruktor initialisiert führt zu unzuverlässige Ergebnissen  
  
 Ein **const** automatische Instanz von einem nicht trivialen Klasse mit einer vom Compiler generierter Standardkonstruktor initialisiert wird.  
  
## <a name="example"></a>Beispiel  
  
```  
// C4269.cpp  
// compile with: /c /LD /W1  
class X {  
public:  
   int m_data;  
};  
  
void g() {  
   const X x1;   // C4269  
};  
```  
  
 Da diese Instanz der Klasse, auf dem Stapel, die den anfänglichen Wert des generiert wird `m_data` kann alles sein. Da es darüber hinaus ist eine **const** Instanz, den Wert der `m_data` nie geändert werden können.