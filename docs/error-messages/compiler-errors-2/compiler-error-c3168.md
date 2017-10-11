---
title: Compiler-Fehler C3168 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3168
dev_langs:
- C++
helpviewer_keywords:
- C3168
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 980341a7871d314e3173449234fbb597a5b55d63
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3168"></a>Compiler-Fehler C3168 generiert
'Typ': Ungültiger zugrunde liegender Typ für Enumeration  
  
Der zugrunde liegende Typ für die `enum` Typ war ungültig. Der zugrunde liegende Typ muss einen ganzzahligen C++-Typ oder einen entsprechenden CLR-Typ.  
  
Im folgende Beispiel wird C3168 generiert:  
  
```  
// C3168.cpp  
// compile with: /clr /c  
ref class G{};  
  
enum class E : G { e };   // C3168  
enum class F { f };   // OK  
```  

