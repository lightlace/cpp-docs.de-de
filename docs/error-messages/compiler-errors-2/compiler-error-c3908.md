---
title: Compilerfehler C3908 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3908
dev_langs:
- C++
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3f971ec355c3f1c3772b2a0cd4059cf0a8abd630
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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