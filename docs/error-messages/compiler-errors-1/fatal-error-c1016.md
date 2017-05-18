---
title: Schwerwiegender Fehler C1016 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1016
dev_langs:
- C++
helpviewer_keywords:
- C1016
ms.assetid: 33f45c3e-2d8f-43ad-a445-c412d1d54ce1
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: b7f9a620f3df21a737736fce943ee750c7171387
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1016"></a>Schwerwiegender Fehler C1016
\##ifdef erwartet ein Bezeichner #ifndef ein Bezeichner erwartet.  
  
 Die bedingte Kompilierungsdirektive ([#ifdef](../../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md) oder `#ifndef`) besitzt keinen Bezeichner zum Auswerten. Geben Sie einen Bezeichner an, um den Fehler zu beheben.  
  
 Im folgenden Beispiel wird C1016 generiert:  
  
```  
// C1016.cpp  
#ifdef   // C1016  
#define FC1016  
#endif  
  
int main() {}  
```  
  
 Mögliche Lösung:  
  
```  
// C1016b.cpp  
#ifdef X  
#define FC1016  
#endif  
  
int main() {}  
```
