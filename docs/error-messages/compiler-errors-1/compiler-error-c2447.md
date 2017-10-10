---
title: Compilerfehler C2447 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2447
dev_langs:
- C++
helpviewer_keywords:
- C2447
ms.assetid: d1bd6e9a-ee42-4510-ae5e-6b0378f7b931
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 20f9e3259b355a40875bd9fc06f04fe2bb3147d0
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2447"></a>Compilerfehler C2447
"{": Funktionskopf fehlt - Parameterliste im alten Stil?  
  
 Der Compiler hat eine unerwartete öffnende geschweifte Klammer im globalen Bereich festgestellt. In den meisten Fällen wird dieser Fehler aufgrund eines falsch formatierten Funktionsheaders, einer falsch platzierten Deklaration oder eines fehlgeleiteten Semikolons verursacht. Stellen Sie zur Behebung dieses Problems sicher, dass die öffnende Klammer einem ordnungsgemäß formatierten Funktionsheader folgt und ihr weder eine Deklaration noch ein fehlgeleitetes Semikolon vorangeht.  
  
 Dieser Fehler kann auch von einer formalen C-Argumentliste im alten Stil verursacht werden. Gestalten Sie zur Behebung dieses Problems die Argumentliste um. Der moderne Stil sieht runde Klammern vor.  
  
 Im folgende Beispiel wird C2447 generiert:  
  
```  
// C2447.cpp  
int c;  
{}       // C2447  
```
