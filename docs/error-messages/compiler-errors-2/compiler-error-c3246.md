---
title: Compiler-Fehler C3246 generiert | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3246
dev_langs:
- C++
helpviewer_keywords:
- C3246
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
caps.latest.revision: 10
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: ac8458487d9ed500420f2e687f8eb7c37bf053da
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3246"></a>Compilerfehler C3246
'klasse': Von 'typ' kann nicht geerbt werden, da er als 'sealed' (versiegelt) deklariert wurde  
  
Eine Klasse, die als gekennzeichnete [versiegelte](../../windows/sealed-cpp-component-extensions.md) kann nicht Basisklasse anderer Klassen verwendet werden.  
  
Im folgenden Beispiel wird C3246 generiert:  
  
```  
// C3246_2.cpp  
// compile with: /clr /LD  
ref class X sealed {};  
  
ref class Y : public X {}; // C3246  
```  

