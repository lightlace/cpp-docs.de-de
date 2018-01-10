---
title: Compilerfehler C2482 | Microsoft Docs
ms.custom: 
ms.date: 09/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2482
dev_langs: C++
helpviewer_keywords: C2482
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c4a5d081e7a19f09f10e40e3799f724f44b295fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2482"></a>Compilerfehler C2482

>"*Bezeichner*": der dynamischen Initialisierung von "Thread" Daten nicht zulässig

Diese Fehlermeldung wird in Visual Studio 2015 und höher veraltet. In früheren Versionen Variablen deklariert, indem die `thread` Attribut kann nicht initialisiert werden, mit einem Ausdruck, der zur Laufzeit Auswertung erfordert. Ein statischer Ausdruck ist erforderlich, um initialisieren `thread` Daten.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C2482 generiert in Visual Studio 2013 und früheren Versionen generiert:

```cpp
// C2482.cpp
// compile with: /c
#define Thread __declspec( thread )
Thread int tls_i = tls_i;   // C2482

int j = j;   // OK in C++; C error
Thread int tls_i = sizeof( tls_i );   // Okay in C and C++
```
