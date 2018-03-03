---
title: Verwenden von VERIFY anstelle ASSERT | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- assert
dev_langs:
- C++
helpviewer_keywords:
- ASSERT statements
- debugging [MFC], ASSERT statements
- VERIFY macro
- assertions, troubleshooting ASSERT statements
- debugging assertions
- assertions, debugging
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4ffe046a281bbbbefc251b48df55ecd275515e60
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-verify-instead-of-assert"></a>Verwenden von VERIFY anstelle ASSERT
Nehmen Sie an, dass beim Ausführen der Debugversion des MFC-Anwendung keine Probleme vorhanden sind. Der endgültigen Produktversion von derselben Anwendung jedoch stürzt ab, gibt falsche Ergebnisse zurück und/oder weist einige andere nicht normales Verhalten auf.  
  
 Dieses Problem kann verursacht werden, wenn Sie wichtigsten Code, in einer ASSERT-Anweisung platzieren, um sicherzustellen, dass er ordnungsgemäß funktioniert. Da der ASSERT-Anweisungen in einem Releasebuild von einem MFC-Programm auskommentiert werden, wird der Code nicht in einem Releasebuild ausgeführt.  
  
 Wenn ASSERT zu verwenden, um zu bestätigen, dass ein Funktionsaufruf erfolgreich war, erwägen Sie [überprüfen](../../mfc/reference/diagnostic-services.md#verify) stattdessen. VERIFY-Makro wertet die eigenen Argumente in sowohl Debug- und Releasebuilds der Anwendung.  
  
 Eine weitere bevorzugte Technik ist, weisen Sie der Funktion zurückgegebene Wert in eine temporäre Variable, und Testen Sie die Variable in einer ASSERT-Anweisung.  
  
 Überprüfen Sie das folgende Codefragment:  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
 Dieser Code wird in einer Debugversion der MFC-Anwendung perfekt ausgeführt. Wenn der Aufruf von `calloc( )` ein Fehler auftritt, wird eine diagnosemeldung aus, die die Anzahl und die Zeilennummer enthält angezeigt. Allerdings in einer Verkaufsversion einer MFC-Anwendung:  
  
-   der Aufruf von `calloc( )` nie auftritt, wenn Sie `buf` nicht initialisiert, oder  
  
-   `strcpy_s( )`Kopien "`Hello, World`" in eine beliebige Stelle des Arbeitsspeichers, die Anwendung möglicherweise abstürzt oder dass das System nicht mehr reagiert, oder  
  
-   `free()`versucht, Arbeitsspeicher freizugeben, die nie zugewiesen wurde.  
  
 Um ASSERT ordnungsgemäß zu verwenden, sollten im Codebeispiel wird wie folgt geändert werden:  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
buf = (char *) calloc(sizeOfBuffer, sizeof(char) );  
ASSERT( buf != NULL );  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
 Oder Sie können überprüfen Sie, ob stattdessen:  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
VERIFY(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Beheben von Problemen mit dem Releasebuild](../../build/reference/fixing-release-build-problems.md)