---
title: Compilerfehler Fehler C2026 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2026
dev_langs: C++
helpviewer_keywords: C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: acee7db1513dd3e999a90218ea674930c2a13f1d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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