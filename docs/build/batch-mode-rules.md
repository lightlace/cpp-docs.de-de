---
title: "Stapelverarbeitungsregeln | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Batchmodus-Rückschlussregeln in NMAKE"
  - "Rückschlussregeln in NMAKE"
  - "NMAKE (Programm), Rückschlussregeln"
ms.assetid: 0650b547-ef19-4455-9bba-fa567dcf88f2
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Stapelverarbeitungsregeln
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

```  
{frompath}.fromext{topath}.toext::  
   commands  
```  
  
 Rückschlussregeln im Batchmodus stellen nur einen Aufruf der Rückschlussregel bereit, wenn *n* Befehle diese Rückschlussregel durchlaufen.  Ohne Rückschlussregeln im Batchmodus müssten *n* Befehle aufgerufen werden.  Dabei ist *n* die Anzahl der abhängigen Dateien, die die Rückschlussregel auslösen.  
  
 Für Makefiles, die Rückschlussregeln im Batchmodus enthalten, muss NMAKE, Version 1.62 oder höher, verwendet werden.  Um die NMAKE\-Version zu überprüfen, wird das **\_NMAKE\_VER**\-Makro ausgeführt, das zusammen mit NMAKE, Version 1.62 oder höher, verfügbar ist.  Dieses Makro gibt eine Zeichenfolge zurück, die die Produktversion von Visual C\+\+ repräsentiert.  
  
 Der einzige syntaktische Unterschied zur Standardrückschlussregel besteht darin, dass die Rückschlussregel im Batchmodus mit zwei Doppelpunkten \(`::`\) beendet wird.  
  
> [!NOTE]
>  Das aufgerufene Tool muss mehrere Dateien verarbeiten können.  Die Rückschlussregel im Batchmodus muss `$<` als Makro für den Zugriff auf abhängige Dateien verwenden.  
  
 Die Rückschlussregeln im Batchmodus können den Buildprozess beschleunigen.  Es ist schneller, dem Compiler die Dateien im Batch anzugeben, da der Compilertreiber dann nur einmal aufgerufen wird.  Der Compiler für C und C\+\+ arbeitet z. B. beim Behandeln eines Dateiensatzes schneller, da der Compiler während des Prozesses speicherresident bleiben kann.  
  
 Im folgenden Beispiel wird gezeigt, wie Rückschlussregeln im Batchmodus verwendet werden:  
  
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
  
 Die folgende Ausgabe wird von NMAKE ohne Rückschlussregeln im Batchmodus generiert:  
  
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
  
 Das folgende Ergebnis wird von NMAKE mit Rückschlussregeln im Batchmodus generiert:  
  
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
  
## Siehe auch  
 [Rückschlussregeln](../build/inference-rules.md)