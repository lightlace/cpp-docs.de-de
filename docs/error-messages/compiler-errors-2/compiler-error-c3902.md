---
title: Compilerfehler C3902 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3902
dev_langs: C++
helpviewer_keywords: C3902
ms.assetid: feb3bb29-f836-4d77-ba71-3876f7f4f216
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ae92650865b4f62fc92c845764bcbfc81db714d1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3902"></a>Compilerfehler C3902
'Accessor': Typ des letzten Parameters muss 'Type'  
  
 Der Typ des letzten Parameters mindestens eine Set-Methode muss dem Typ der Eigenschaft entsprechen. Weitere Informationen finden Sie unter [property](../../windows/property-cpp-component-extensions.md).  
  
 Im folgende Beispiel wird C3902 generiert:  
  
```  
// C3902.cpp  
// compile with: /clr /c  
using namespace System;  
ref class X {  
   property String ^Name {  
      void set(int);   // C3902  
      // try the following line instead  
      // void set(String^){}  
   }  
  
   property double values[int,int] {  
      void set(int, int, float);   // C3902  
      // try the following line instead  
      // void set(int, int, double){}  
   }  
};  
```