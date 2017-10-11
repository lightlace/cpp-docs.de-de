---
title: Compilerfehler Fehler C2026 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2026
dev_langs:
- C++
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 97937579c12730fecfa89c69d9e7cf51229b5c6c
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2026"></a>Compilerfehler Fehler C2026
Zeichenfolge zu lang, nachfolgende Zeichen gekürzt  
  
 Die Zeichenfolge wurde länger als das Limit von 16380 Einzelbyte-Zeichen.  
  
 Vor der angrenzenden Zeichenfolgen verkettet werden darf keine Zeichenfolge länger als 16380 Einzelbyte-Zeichen sein.  
  
 Eine Unicode-Zeichenfolge mit ungefähr die Hälfte dieser Länge würde auch dieser Fehler generiert.  
  
 Wenn Sie eine Zeichenfolge, die wie folgt definiert haben, wird es C2026 generiert:  
  
```  
char sz[] =  
"\  
imagine a really, really \  
long string here\  
";  
```  
  
 Sie können es wie folgt zusammensetzen:  
  
```  
char sz[] =  
"\  
imagine a really, really "  
"long string here\  
";  
```  
  
 Sie wollen außergewöhnlich große Zeichenfolgenliterale (32 KB oder mehr) speichern in einer benutzerdefinierten Ressource oder eine externe Datei. Finden Sie unter [Erstellen einer neuen benutzerdefinierten Ressource oder Datenressource](../../windows/creating-a-new-custom-or-data-resource.md) für Weitere Informationen.
