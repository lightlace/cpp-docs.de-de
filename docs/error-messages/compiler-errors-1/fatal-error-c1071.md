---
title: Schwerwiegender Fehler C1071 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1071
dev_langs:
- C++
helpviewer_keywords:
- C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: acd48401d3abc17d994e861bf6fb046450d88ca6
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1071"></a>Schwerwiegender Fehler C1071
Unerwartetes Dateiende innerhalb eines Kommentars  
  
 Der Compiler hat beim Scannen eines Kommentars das Ende der Datei erreicht.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Kommentar Abschlusszeichen fehlt (* /).  
  
2.  Fehlende Zeilenendemarke nach einem Kommentar in der letzten Zeile einer Quelldatei.  
  
 Im folgenden Beispiel wird C1071 generiert:  
  
```  
// C1071.cpp  
int main() {  
}  
  
/* this comment is fine */  
/* forgot the closing tag        // C1071  
```
