---
title: "Einschränken | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: restrict_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], restrict
- restrict __declspec keyword
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9176336ac96d88a34d758fd55c09a3a938f371fb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="restrict"></a>restrict
**Microsoft-spezifisch**  
  
 Angewendet auf eine Funktionsdeklaration oder eine Definition, die einen Zeigertyp zurückgibt und dem Compiler mitgeteilt, dass die Funktion ein Objekt zurückgibt, das keinen Alias mit anderen Zeigern besitzt.  
  
## <a name="syntax"></a>Syntax  
  
```  
__declspec(restrict) return_type f();  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Compiler gibt `__declspec(restrict)` weiter. Beispielsweise wird die CRT-Funktion `malloc` mit `__declspec(restrict)` ausgestattet. Daher wird auch impliziert, dass initialisierte Zeiger auf Speicheradressen `malloc` nicht mit einem Alias versehen werden.  
  
 Der Compiler überprüft nicht, ob der Zeiger tatsächlich keinen Alias besitzt. Es liegt in der Verantwortung des Entwicklers, sicherzustellen, dass das Programm einem Zeiger, der mit dem `restrict __declspec`-Modifizierer markiert ist, keinen Alias zuweist.  
  
 Ähnliche Semantik für Variablen finden Sie unter [__restrict](../cpp/extension-restrict.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Noalias](../cpp/noalias.md) ein Beispiel mit `restrict`.  
  
 Informationen zum Beschränken-Schlüsselwort, das Bestandteil des C++ AMP ist, finden Sie unter [einschränken (C++-AMP)](../cpp/restrict-cpp-amp.md).  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [__declspec](../cpp/declspec.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)