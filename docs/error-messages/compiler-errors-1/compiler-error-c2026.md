---
title: Compiler-Fehler C2026 | Microsoft-Dokumentation
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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: c429f81c64b7710b7edc2b8540d98e8c790e4062
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2026"></a>Compiler-Fehler C2026
Zeichenfolge zu lang, Zeichen am Ende wurden entfernt  
  
 Die Zeichenfolge ist länger als der maximal 16380 Einzelbytezeichen.  
  
 Vor angrenzende Zeichenfolgen verkettet werden darf keine Zeichenfolge maximal 16380 Einzelbyte-Zeichen lang sein.  
  
 Eine Unicode-Zeichenfolge von ungefähr halb so lang würde auch diese Fehler generiert.  
  
 Wenn Sie eine Zeichenfolge, die wie folgt definiert haben, wird es C2026:  
  
```  
char sz[] =  
"\  
imagine a really, really \  
long string here\  
";  
```  
  
 Sie könnten es wie folgt aufteilen:  
  
```  
char sz[] =  
"\  
imagine a really, really "  
"long string here\  
";  
```  
  
 Möglicherweise möchten Sie zum Speichern von sehr umfangreiche Zeichenfolgenliterale (32 KB oder mehr) aus einer benutzerdefinierten Ressource oder eine externe Datei. Finden Sie unter [Erstellen einer neuen benutzerdefinierten Ressource oder Datenressource](../../windows/creating-a-new-custom-or-data-resource.md) Weitere Informationen.
