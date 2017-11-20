---
title: Stapelverarbeitungsregeln | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inference rules in NMAKE
- NMAKE program, inference rules
- batch-mode inference rules in NMAKE
ms.assetid: 0650b547-ef19-4455-9bba-fa567dcf88f2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: be8c00009e285ec84f42ae6f53c578a3084432de
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="batch-mode-rules"></a>Stapelverarbeitungsregeln
```  
{frompath}.fromext{topath}.toext::  
   commands  
```  
  
 Batchmodus Rückschlussregeln geben nur einen einzelnen Aufruf der Rückschlussregel aus, wenn N Befehle diese Rückschlussregel durchlaufen. Ohne Batchmodus Rückschlussregeln müssten N Befehle aufgerufen werden. N ist die Anzahl der abhängigen Elemente, die die Rückschlussregel auslösen.  
  
 Makefiles, die im Batchmodus-Rückschlussregeln enthalten müssen NMAKE Version 1.62 oder höher verwenden. Um die NMAKE-Version zu überprüfen, führen Sie die verfügbaren Makros _NMAKE_VER mit NMAKE Version, 1.62 oder höher. Dieses Makro gibt eine Zeichenfolge, die Visual C++-Produktversion darstellt.  
  
 Der nur syntaktische Unterschied aus standard Rückschlussregel ist, dass die Rückschlussregel im Batchmodus mit zwei Doppelpunkten (:) beendet wurde.  
  
> [!NOTE]
>  Das aufgerufene Tool muss mehrere Dateien behandelt werden können. Rückschlussregel im Batchmodus Striches `$<` als Makro auf abhängige Dateien zugreifen.  
  
 Der Batchmodus Rückschlussregeln können während des Erstellungsprozesses beschleunigen. Ist es schneller, geben Sie die Dateien an den Compiler im Batch, da der Compilertreiber nur einmal aufgerufen wird. Beispielsweise bietet der C- und C++-Compiler eine bessere Leistung bei der Behandlung von einen Satz von Dateien, da es während des Prozesses speicherresident bleiben kann.  
  
 Im folgende Beispiel wird gezeigt, wie im Batchmodus-Rückschlussregeln verwendet wird:  
  
```  
#  
# sample makefile to illustrate batch-mode inference rules  
#  
O = .  
S = .  
Objs = $O/foo1.obj $O/foo2.obj $O/foo2.obj $O/foo3.obj $O/foo4.obj  
CFLAGS = -nologo  
  
all : $(Objs)  
  
!ifdef NOBatch  
{$S}.cpp{$O}.obj:  
!else  
{$S}.cpp{$O}.obj::  
!endif  
   $(CC) $(CFLAGS) -Fd$O\ -c $<  
  
$(Objs) :  
  
#end of makefile  
```  
  
 NMAKE erzeugt die folgende Ausgabe ohne Batchmodus Rückschlussregeln:  
  
```  
E:\tmp> nmake -f test.mak -a NOBatch=1  
  
Microsoft (R) Program Maintenance Utility   Version 7.00.0000  
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.  
        cl -nologo -Fd.\ -c .\foo1.cpp  
foo1.cpp  
        cl -nologo -Fd.\ -c .\foo2.cpp  
foo2.cpp  
        cl -nologo -Fd.\ -c .\foo3.cpp  
foo3.cpp  
        cl -nologo -Fd.\ -c .\foo4.cpp  
foo4.cpp  
```  
  
 NMAKE führt zu folgendem Ergebnis mit den Batchmodus Rückschlussregeln:  
  
```  
E:\tmp> nmake -f test.mak -a  
  
Microsoft (R) Program Maintenance Utility   Version 7.00.0000  
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.  
  
        cl -nologo -Fd.\ -c .\foo1.cpp .\foo2.cpp .\foo3.cpp .\foo4.cpp  
foo1.cpp  
foo2.cpp  
foo3.cpp  
foo4.cpp  
Generating Code...  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Rückschlussregeln](../build/inference-rules.md)