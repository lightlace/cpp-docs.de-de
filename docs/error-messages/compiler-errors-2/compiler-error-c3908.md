---
title: Compilerfehler C3908 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3908
dev_langs: C++
helpviewer_keywords: C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 05b4f772c5c1acf8da9247f27fa92a947a0ffc5b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3908"></a>Compilerfehler C3908
die Zugriffsebene ist weniger restriktiv ist als 'Konstrukt'  
  
 Eine Eigenschaft Accessor-Methode (Get oder Set) sind keine weniger restriktiven Zugriff als der Zugriff auf die Eigenschaft selbst.  Ähnlich gilt für Methoden des Eigenschaftenaccessors.  
  
 Weitere Informationen finden Sie unter [Eigenschaft](../../windows/property-cpp-component-extensions.md) und [Ereignis](../../windows/event-cpp-component-extensions.md).  
  
 Im folgende Beispiel wird C3908 generiert:  
  
```  
// C3908.cpp  
// compile with: /clr  
ref class X {  
protected:  
   property int i {  
   public:   // C3908 property i is protected   
      int get();  
   private:  
      void set(int);   // OK more restrictive  
   };  
};  
```