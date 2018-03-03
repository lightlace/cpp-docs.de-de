---
title: Linkertoolwarnung Lnk4247 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4247
dev_langs:
- C++
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 517605993199942f863faa78e14a022529214a64
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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