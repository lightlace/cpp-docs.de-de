---
title: Compilerwarnung C4693 | Microsoft Docs
ms.date: 10/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4693
dev_langs: C++
helpviewer_keywords: C4693
ms.assetid: 72d8db01-5e6f-4794-8731-76107e8f064a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3e5d7b93295505d989e651500dda0664c1a13a36
ms.sourcegitcommit: 69632887f7a85f4841c49b4c1353d3144927a52c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2017
---
# <a name="compiler-warning-c4693"></a>Compilerwarnung C4693

> "class": Eine versiegelte abstrakte Klasse kann keine Test-Instanzmember aufweisen

Wenn ein Typ gekennzeichnet ist [versiegelten](../../windows/sealed-cpp-component-extensions.md) und [abstrakte](../../windows/abstract-cpp-component-extensions.md), es kann nur statische Member aufweisen.

Diese Warnung wird automatisch zu einem Fehler heraufgestuft. Wenn Sie dieses Verhalten ändern möchten, verwenden Sie [#pragma Warning](../../preprocessor/warning.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4693 generiert:

```cpp
// C4693.cpp
// compile with: /clr /c
public ref class Public_Ref_Class sealed abstract {
public:
   void Test() {}   // C4693
   static void Test2() {}   // OK
};
```