---
title: Compiler-Fehler C2757 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2757
dev_langs: C++
helpviewer_keywords: C2757
ms.assetid: 421f102f-8a32-4d47-a109-811ddf2c909d
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e10d357679fc7a0d1a5e183bdc1eb95a7a597c00
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2757"></a>Compiler-Fehler C2757 generiert
'Symbol': ein Symbol mit diesem Namen bereits vorhanden ist und aus diesem Grund kann dieser Name als ein Namespacename verwendet werden  
  
 Ein Symbol in der aktuellen Kompilierung verwendet werden, wie ein Namespacebezeichner in einer referenzierten Assembly bereits verwendet wird.  
  
 Im folgende Beispiel wird C2757 generiert:  
  
```  
// C2757a.cpp  
// compile with: /clr /LD  
public ref class Nes {};  
```  
  
 und anschließend  
  
```  
// C2757b.cpp  
// compile with: /clr /c  
#using <C2757a.dll>  
  
namespace Nes {    // C2757  
// try the following line instead  
// namespace Nes2 {  
   public ref class X {};  
}  
```  
