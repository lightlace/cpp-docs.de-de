---
title: Linkertoolwarnung Lnk4247 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4247
dev_langs:
- C++
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6096bbfba9c60d8ed28aa660d078cd155f0316a3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4247"></a>Linkertoolwarnung LNK4247
Einstiegspunkt 'Decorated_function_name"verfügt bereits über eine Thread-Attribut; 'Attribut' wird ignoriert  
  
 Einstiegspunkt mit angegebenen [/Entry (Symbol für Einstiegspunkt)](../../build/reference/entry-entry-point-symbol.md), wies ein Threadattribut jedoch [/CLRTHREADATTRIBUTE (festlegen CLR-Thread-Attribut)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md) wurde auch angegeben, mit einem anderen Threadingmodell.  
  
 Der Linker ignoriert den Wert mit/CLRTHREADATTRIBUTE angegeben.  
  
 Um diese Warnung zu beheben:  
  
-   / CLRTHREADATTRIBUTE aus einem Build zu entfernen.  
  
-   Entfernen Sie Attribut aus der Quellcodedatei.  
  
-   Entfernen Sie das Attribut von Quelle und/CLRTHREADATTRIBUTE aus einem Build, und akzeptieren Sie die Standard-CLR-Threadingmodell.  
  
-   Ändern Sie den Wert, der an/CLRTHREADATTRIBUTE, übergeben, so, dass er mit dem Attribut in der Quelle zustimmt.  
  
-   Ändern Sie das Attribut in der Quelle, so, dass er mit dem Wert, der an/CLRTHREADATTRIBUTE übergebenen zustimmt.  
  
 Im folgenden Beispiel wird LNK4247  
  
```  
// LNK4247.cpp  
// compile with: /clr /c  
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console  
 [System::MTAThreadAttribute]  
void functionTitle (){}  
```