---
title: Schwerwiegender Fehler C1308 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1308
dev_langs:
- C++
helpviewer_keywords:
- C1308
ms.assetid: 46177997-069e-433a-8e20-93c846d78ffd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dca537131f111c02dd642dff869510eca788b9a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1308"></a>Schwerwiegender Fehler C1308
Verknüpfen von Assemblys wird nicht unterstützt.  
  
 Eine NETMODULE-Datei als Eingabe für den Linker zulässig ist, aber eine Assembly ist. Dieser Fehler kann generiert werden, wenn versucht wird, verknüpfen Sie eine Assembly kompiliert, die mit `/clr:safe`.  
  
 Weitere Informationen finden Sie unter [NETMODULE-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md).  
  
 Im folgenden Beispiel wird C1308 generiert:  
  
```  
// C1308.cpp  
// compile with: /clr:safe /LD  
public ref class MyClass {  
public:  
   int i;  
};  
```  
  
 Und dann  
  
```  
// C1308b.cpp  
// compile with: /clr /link C1308b.obj C1308.dll  
// C1308 expected  
#using "C1308.dll"  
int main() {  
   MyClass ^ my = gcnew MyClass();  
}  
```