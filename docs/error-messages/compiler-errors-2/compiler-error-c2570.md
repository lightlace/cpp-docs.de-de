---
title: Compilerfehler C2570 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2570
dev_langs:
- C++
helpviewer_keywords:
- C2570
ms.assetid: d65d0b32-2fac-464a-bcdf-0ebcedf3bf32
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5b870ddd8bb162f4f65bd3200c397f912249304b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33228302"
---
# <a name="compiler-error-c2570"></a>Compilerfehler C2570
'Bezeichner': Union sind keine Basisklassen  
  
 Eine Union leitet sich von einer Klasse, Struktur oder Union. Dies ist nicht zulässig. Deklarieren Sie stattdessen den abgeleiteten Typ als eine Klasse oder Struktur.  
  
 Im folgenden Beispiel wird C2570 generiert:  
  
```  
// C2570.cpp  
// compile with: /c  
class base {};  
union hasPubBase : public base {};   // C2570  
union hasNoBase {};   // OK  
```