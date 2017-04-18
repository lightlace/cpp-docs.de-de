---
title: Compiler (Stufe 1) C4165 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4165
dev_langs:
- C++
helpviewer_keywords:
- C4165
ms.assetid: f5bed515-2290-4f88-8dab-b45d95fe26ef
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 4ac033535632e94a365aa8dafd849f2ab28a3af7
ms.openlocfilehash: 9f2007a2f43cd7641979b663c58efb3a8e276246
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4165"></a>Compiler (Stufe 1) C4165
"HRESULT" wird zu "bool" konvertiert. Möchten Sie diese Änderung wirklich vornehmen?  
  
Bei Verwendung von HRESULT in ein [Wenn](../../cpp/if-else-statement-cpp.md) -Anweisung wird das HRESULT in konvertiert eine [Bool](../../cpp/bool-cpp.md) explizit für die Variable als ein HRESULT testen. Diese Warnung ist standardmäßig deaktiviert.  
  
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
