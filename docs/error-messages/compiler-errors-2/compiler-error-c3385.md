---
title: Compilerfehler C3385 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3385
dev_langs:
- C++
helpviewer_keywords:
- C3385
ms.assetid: 5f1838c1-986e-47db-8dbc-e06976b83cf3
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9fca91679b6e66ffcaefe5bc169a4889f032cf55
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3385"></a>Compilerfehler C3385
'Klasse::Funktion': Eine Funktion, die ein benutzerdefiniertes DllImport-Attribut hat, kann keine Instanz einer Klasse zurückgeben.  
  
 Eine Funktion, die als Teil einer DLL-Datei definiert wird, die mit dem `DllImport` -Attribut angegeben wurde, kann keine Instanz einer Klasse zurückgeben.  
  
 Im folgenden Beispiel wird C3385 generiert:  
  
```  
// C3385.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
struct SomeStruct1 {};  
  
public ref struct Wrap {  
   [ DllImport("somedll.dll", CharSet=CharSet::Unicode) ]  
   static SomeStruct1 f1([In, Out] SomeStruct1 *pS);   // C3385  
};  
```  
