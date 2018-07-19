---
title: Compiler-Fehler C2790 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2790
dev_langs:
- C++
helpviewer_keywords:
- C2790
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11f1c90fed93666fad7513e2b4186a5baa2aa406
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33232816"
---
# <a name="compiler-error-c2790"></a>Compiler-Fehler C2790 generiert
"Superuser": Dieses Schlüsselwort kann nur innerhalb eines Texts der Klassenmemberfunktion verwendet werden  
  
 Diese Fehlermeldung wird angezeigt, wenn der Benutzer versucht, verwendet das Schlüsselwort [super](../../cpp/super.md) außerhalb des Kontexts einer Memberfunktion.  
  
 Im folgende Beispiel wird C2790 generiert:  
  
```  
// C2790.cpp  
void f() {  
   __super::g();   // C2790  
}  
```