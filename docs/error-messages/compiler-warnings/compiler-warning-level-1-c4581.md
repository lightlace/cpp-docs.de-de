---
title: Compilerwarnung (Stufe 1) C4581 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4581
dev_langs:
- C++
helpviewer_keywords:
- C4581
ms.assetid: 598bcd87-257d-4eb3-94e4-15bb31aadc99
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 415fb9ffc3e53ddfe9edcee2ec99361b38de0dea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281858"
---
# <a name="compiler-warning-level-1-c4581"></a>Compilerwarnung (Stufe 1) C4581
Verhalten veraltet: "string1" ersetzt durch "Zeichenfolge2" Prozess-Attribut  
  
 Dieser Fehler kann infolge einer konformitätsverbesserung für Visual C++ 2005 erstellt wurde, die generiert werden: Überprüfen der Parameter für Visual C++-Attribute.  
  
 In früheren Versionen wurden Attributwerte akzeptiert, und zwar unabhängig davon, ob sie in Anführungszeichen eingeschlossen wurden. Wenn der Wert einer Enumeration ist, muss er nicht in Anführungszeichen eingeschlossen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4581 generiert.  
  
```  
// C4581.cpp  
// compile with: /c /W1  
#include "unknwn.h"  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI : IUnknown {};  
  
[coclass, uuid(12345678-1111-2222-3333-123456789012), threading("free")]   // C4581  
// try the following line instead  
// [coclass, uuid(12345678-1111-2222-3333-123456789012), threading(free)]  
class CSample : public IMyI {};  
```