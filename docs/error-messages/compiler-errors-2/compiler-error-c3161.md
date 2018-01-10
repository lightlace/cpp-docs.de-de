---
title: Compiler-Fehler C3161 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3161
dev_langs: C++
helpviewer_keywords: C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c0cdbbd9364435ebcfad114331b6ba7289cb8010
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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