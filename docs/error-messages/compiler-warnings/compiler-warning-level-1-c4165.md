---
title: Compilerwarnung (Stufe 1) C4165 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4165
dev_langs:
- C++
helpviewer_keywords:
- C4165
ms.assetid: f5bed515-2290-4f88-8dab-b45d95fe26ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39487999f2aa74a5600d84d71917712e03b2d626
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4165"></a>Compilerwarnung (Stufe 1) C4165
'HRESULT' wird "Bool" konvertiert sind Sie sicher, dass dies gewünscht ist?  
  
Bei Verwendung von HRESULT in ein [Wenn](../../cpp/if-else-statement-cpp.md) -Anweisung wird das HRESULT konvertiert ein [Bool](../../cpp/bool-cpp.md) es sei denn, Sie explizit für die Variable als ein HRESULT zu testen. Diese Warnung ist standardmäßig deaktiviert.  
  
## <a name="example"></a>Beispiel  
Im folgende Beispiel wird C4165 generiert.  
  
```cpp  
// C4165.cpp  
// compile with: /W1  
#include <windows.h>  
#pragma warning(1:4165)  
  
extern HRESULT hr;  
int main() {  
   if (hr) {  
   // try either of the following ...  
   // if (FAILED(hr)) { // C4165 expected  
   // if (hr != S_OK) {  
   }  
}  
```