---
title: "Beispielmakefile f&#252;r PCH"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "pch"
dev_langs: 
  - "C++"
ms.assetid: daf68983-77dc-45db-8701-aa89ad18910d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Beispielmakefile f&#252;r PCH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Im folgenden Makefile werden Makros sowie eine aus den Befehlen **\!IF**, **\!ELSE** und `!ENDIF` bestehende Befehlsstruktur verwendet, um die Anpassung an das Projekt zu vereinfachen.  
  
```  
# Makefile : Illustrates the effective use of precompiled  
#            headers in a project  
# Usage:     NMAKE option  
# option:    DEBUG=[0|1]  
#            (DEBUG not defined is equivalent to DEBUG=0)  
#  
OBJS = myapp.obj applib.obj  
# List all stable header files in the STABLEHDRS macro.  
STABLEHDRS = stable.h another.h  
# List the final header file to be precompiled here:  
BOUNDRY = stable.h  
# List header files under development here:  
UNSTABLEHDRS = unstable.h  
# List all compiler options common to both debug and final  
# versions of your code here:  
CLFLAGS = /c /W3  
# List all linker options common to both debug and final  
# versions of your code here:  
LINKFLAGS = /NOD /ONERROR:NOEXE  
!IF "$(DEBUG)" == "1"  
CLFLAGS   = /D_DEBUG $(CLFLAGS) /Od /Zi /f  
LINKFLAGS = $(LINKFLAGS) /COD  
LIBS      = slibce  
!ELSE  
CLFLAGS   = $(CLFLAGS) /Oselg /Gs  
LINKFLAGS = $(LINKFLAGS)  
LIBS      = slibce  
!ENDIF  
myapp.exe: $(OBJS)  
    link $(LINKFLAGS) @<<  
$(OBJS), myapp, NUL, $(LIBS), NUL;  
<<  
# Compile myapp  
myapp.obj  : myapp.cpp $(UNSTABLEHDRS)  stable.pch  
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    myapp.cpp  
# Compile applib  
applib.obj : applib.cpp $(UNSTABLEHDRS) stable.pch  
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    applib.cpp  
# Compile headers  
stable.pch : $(STABLEHDRS)  
    $(CPP) $(CLFLAGS) /Yc$(BOUNDRY)    applib.cpp myapp.cpp  
```  
  
 Neben den Makros **STABLEHDRS**, **BOUNDRY** und **UNSTABLEHDRS**, die in der Abbildung "Struktur eines Makefiles, das eine vorkompilierte Headerdatei verwendet" unter [PCH\-Dateien im Erstellungsvorgang](../../build/reference/pch-files-in-the-build-process.md) dargestellt sind, bietet dieses Makefile ein **CLFLAGS**\-Makro sowie ein **LINKFLAGS**\-Makro.  Diese Makros müssen verwendet werden, wenn Sie Compiler\- und Linkeroptionen auflisten möchten, die beim Erstellen einer Debug\- oder einer endgültigen Version der ausführbaren Programmdatei benötigt werden.  Darüber hinaus wird ein **LIBS**\-Makro verwendet, in dem die für das Projekt erforderlichen Bibliotheken aufgeführt werden.  
  
 Das Makefile verwendet zusätzlich **\!IF**, **\!ELSE** und `!ENDIF`, um festzustellen, ob Sie ein **DEBUG**\-Symbol in der **NMAKE**\-Befehlszeile definieren:  
  
```  
NMAKE DEBUG=[1|0]  
```  
  
 Dadurch haben Sie die Möglichkeit, bei der Entwicklung und für die endgültigen Programmversionen dasselbe Makefile zu verwenden. Verwenden Sie **DEBUG\=0** für die endgültigen Versionen.  Die nachfolgenden Befehlszeilen sind identisch:  
  
```  
NMAKE   
NMAKE DEBUG=0  
```  
  
 Weitere Informationen zu Makefiles finden Sie in der [NMAKE\-Referenz](../../build/nmake-reference.md).  Beachten Sie auch die [Compileroptionen](../../build/reference/compiler-options.md) und [Linkeroptionen](../../build/reference/linker-options.md).  
  
## Siehe auch  
 [Verwenden von vorkompilierten Headern in einem Projekt](../../build/reference/using-precompiled-headers-in-a-project.md)