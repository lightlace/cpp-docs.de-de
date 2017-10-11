---
title: Compilerfehler C2569 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2569
dev_langs:
- C++
helpviewer_keywords:
- C2569
ms.assetid: 092bed1e-f631-436c-9586-7750629f6fac
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cf7df87144b664463f577360dac13af2d3006c8b
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2569"></a>Compilerfehler C2569
'EnumOderUnion': Enumeration/Union kann nicht als Basisklasse verwendet werden  
  
 Wenn Sie einen Typ aus der angegebenen Union oder Enumeration abgeleitet werden müssen, ändern Sie die Union oder Enumeration zu einer Klasse oder Struktur an.  
  
 Im folgende Beispiel wird C2569 generiert:  
  
```  
// C2569.cpp  
// compile with: /c  
union ubase {};  
class cHasPubUBase : public ubase {};   // C2569  
// OK  
struct sbase {};  
class cHasPubUBase : public sbase {};  
```
