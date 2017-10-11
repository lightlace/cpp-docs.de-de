---
title: Compilerfehler C3246 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3246
dev_langs:
- C++
helpviewer_keywords:
- C3246
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 262dc8bde5dcb4c12909c69bce3fa867685245eb
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3246"></a>Compilerfehler C3246
'klasse': Von 'typ' kann nicht geerbt werden, da er als 'sealed' (versiegelt) deklariert wurde  
  
Eine Klasse, die als [versiegelt](../../windows/sealed-cpp-component-extensions.md) gekennzeichnet ist, kann nicht die Basisklasse für andere Klassen bilden.  
  
Im folgenden Beispiel wird C3246 generiert:  
  
```  
// C3246_2.cpp  
// compile with: /clr /LD  
ref class X sealed {};  
  
ref class Y : public X {}; // C3246  
```  

