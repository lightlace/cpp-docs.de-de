---
title: Compilerwarnung (Stufe 1) C4165 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4165
dev_langs: C++
helpviewer_keywords: C4165
ms.assetid: f5bed515-2290-4f88-8dab-b45d95fe26ef
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e31f0e0440b0c31197ded21464edc9d686c4864e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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