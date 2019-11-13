---
title: Compilerwarnung (Stufe 2) C4156
ms.date: 11/04/2016
f1_keywords:
- C4156
helpviewer_keywords:
- C4156
ms.assetid: 9adf3acb-c0fe-42a8-a4db-5822b1493f77
ms.openlocfilehash: 95605aa29e1faba449e19dcf20e6895d31cc5874
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052145"
---
# <a name="compiler-warning-level-2-c4156"></a>Compilerwarnung (Stufe 2) C4156

Löschen eines Array Ausdrucks ohne Verwendung der Arrayform von "Delete" Ersetzen eines Array Formulars

Die nicht-Array-Form von **Delete** kann ein Array nicht löschen. Der Compiler hat **Delete** in das Array Formular übersetzt.

Diese Warnung tritt nur unter Microsoft-Erweiterungen (/Ze) auf.

## <a name="example"></a>Beispiel

```cpp
// C4156.cpp
// compile with: /W2
int main()
{
   int (*array)[ 10 ] = new int[ 5 ][ 10 ];
   delete array; // C4156, changed by compiler to "delete [] array;"
}
```