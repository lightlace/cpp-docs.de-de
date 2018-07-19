---
title: Compiler-Fehler C3161 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3161
dev_langs:
- C++
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f2d7aff3eb41c03f5be774704922340ac54126fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33250702"
---
# <a name="compiler-error-c3161"></a>Compiler-Fehler C3161 generiert
'Schnittstelle': Schachteln von Klasse, Struktur, Union oder eine Schnittstelle in einer Schnittstelle ist nicht zulässig. Schachteln einer Schnittstelle in einer Klasse, Struktur oder Union ist nicht zulässig  
  
 Ein [__interface](../../cpp/interface.md) kann nur verwendet werden, im globalen Gültigkeitsbereich oder innerhalb eines Namespace. Eine Klasse, Struktur oder Union kann nicht in einer Schnittstelle angezeigt.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3161 generiert.  
  
```  
// C3161.cpp  
// compile with: /c  
__interface X {  
   __interface Y {};   // C3161 A nested interface  
};  
```