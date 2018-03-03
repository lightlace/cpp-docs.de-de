---
title: Compilerfehler C3247 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3247
dev_langs:
- C++
helpviewer_keywords:
- C3247
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1c3b694129e28351db1aff1367187ceab052eb52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3247"></a>Compilerfehler C3247
'Klasse1': Eine Co-Klasse kann nicht von einer anderen Co-Klasse 'Klasse2' erben.  
  
 Eine Klasse mit dem [coclass](../../windows/coclass.md) -Attribut gekennzeichnete Klasse kann nicht von einer anderen Klasse erben, die mit dem `coclass` -Attribut markiert ist.  
  
 Im folgenden Beispiel wird C3247 generiert:  
  
```  
// C3247.cpp  
[module(name="MyLib")];  
[coclass]  
class a {  
};  
  
[coclass]  
class b : public a {   // C3247  
};  
int main() {  
}  
```