---
title: Compilerwarnung C4687 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4687
dev_langs:
- C++
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ad45c4bb2456b3bc23114233c084bbad1551e27
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272720"
---
# <a name="compiler-warning-c4687"></a>Compilerwarnung C4687
'Klasse': eine versiegelte abstrakte Klasse kann nicht implementiert eine Schnittstelle "Schnittstelle"  
  
 Ein Typ versiegelter "," abstract ist in der Regel nur nützlich, um statische Memberfunktionen enthalten.  
  
 Weitere Informationen finden Sie unter [abstrakte](../../windows/abstract-cpp-component-extensions.md)und [versiegelten](../../windows/sealed-cpp-component-extensions.md).  
  
 C4687 wird standardmäßig als Fehler ausgegeben. Sie können C4687 mit Unterdrücken der [Warnung](../../preprocessor/warning.md) Pragma. Wenn Sie sicher sind, dass Sie eine Schnittstelle in einem versiegelten "," abstract Typ implementieren möchten, können Sie C4687 unterdrücken.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4687 generiert.  
  
```  
// C4687.cpp  
// compile with: /clr /c  
interface class A {};  
  
ref struct B sealed abstract : A {};   // C4687  
ref struct C sealed : A {};   // OK  
ref struct D abstract : A {};   // OK  
```