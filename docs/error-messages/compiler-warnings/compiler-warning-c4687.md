---
title: Compilerwarnung C4687 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4687
dev_langs:
- C++
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 266213deba94bdc925747d57dee184aca5f5f605
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

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
