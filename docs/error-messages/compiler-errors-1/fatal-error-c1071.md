---
title: Schwerwiegender Fehler C1071 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1071
dev_langs:
- C++
helpviewer_keywords:
- C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9cef64c327c0fd3b668947de52f2776cca2833c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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