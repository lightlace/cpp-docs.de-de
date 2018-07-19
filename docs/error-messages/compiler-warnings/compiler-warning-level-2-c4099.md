---
title: Compilerwarnung (Stufe 2) C4099 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4099
dev_langs:
- C++
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: afecb3fb2420d27bedf16c81894f224a1119a67b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33309467"
---
# <a name="compiler-warning-level-2-c4099"></a>Compilerwarnung (Stufe 2) C4099
'Bezeichner': Typnamen, die mit 'Objekttyp1 ' und jetzt mithilfe von "%objecttype2" für die erstmalige Sichtbarkeit  
  
 Ein Objekt, das als Struktur deklariert wird als Klasse definiert, oder ein Objekt als eine Klasse deklariert wird als Struktur definiert. Der Compiler verwendet den Typ in der Definition.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4099 generiert.  
  
```  
// C4099.cpp  
// compile with: /W2 /c  
struct A;  
class A {};   // C4099, use different identifer or use same object type  
```