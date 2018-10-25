---
title: Compilerfehler C2842 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2842
dev_langs:
- C++
helpviewer_keywords:
- C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f6143249871384d89227d63fe1900814ae5077fd
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055241"
---
# <a name="compiler-error-c2842"></a>Compilerfehler C2842

„Klasse“: Ein verwalteter oder WinRT-Typ kann keinen eigenen „operator new“- oder „operator delete“-Operator definieren.

Sie können definieren, Ihre eigenen ** new-Operator oder **Delete-Operator** speicherbelegung auf dem systemeigenen Heap zu verwalten. Verweisklassen können diese Operatoren jedoch nicht definieren, da sie nur dem verwalteten Heap zugewiesen sind.

Weitere Informationen finden Sie unter [User-Defined Operators (C++ / CLI)](../../dotnet/user-defined-operators-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2842 generiert.

```
// C2842.cpp
// compile with: /clr /c
ref class G {
   void* operator new( size_t nSize );   // C2842
};
```
