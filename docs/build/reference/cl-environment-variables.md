---
title: "CL-Umgebungsvariablen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe-Compiler, Umgebungsvariablen"
  - "Umgebungsvariablen, CL-Compiler"
  - "INCLUDE-Umgebungsvariable"
  - "LIBPATH-Umgebungsvariable"
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# CL-Umgebungsvariablen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das CL\-Tool verwendet die folgenden Umgebungsvariablen:  
  
-   CL und \_CL\_, falls definiert.  Das CL\-Tool stellt die in der CL\-Umgebungsvariable für die Befehlszeilenargumente definierten Optionen und Argumente voran, und fügt die in „\_CL\_“ definierten Optionen und Argumente vor der Verarbeitung an.  
  
-   INCLUDE: Hierbei muss es sich um den Punkt zu Ihrem „\\include“\-Unterverzeichnis Ihrer Visual C\+\+\-Installation handeln.  
  
-   LIBPATH: Gibt Verzeichnisse zum Suchen nach Metadatendateien an, die mit [\#using](../../preprocessor/hash-using-directive-cpp.md) referenziert werden.  Weitere Informationen über LIBPATH finden Sie unter `#using`.  
  
 Mithilfe der folgenden Syntax können Sie die Umgebungsvariable „CL“ oder „\_CL\_“ festlegen:  
  
```  
SET CL=[ [option] ... [file] ...] [/link link-opt ...]  
SET _CL_=[ [option] ... [file] ...] [/link link-opt ...]  
```  
  
 Ausführliche Informationen über die Argumente für die Umgebungsvariablen „CL“ und „\_CL\_“ finden Sie unter [Syntax für die Compilerbefehlszeile](../../build/reference/compiler-command-line-syntax.md).  
  
 Sie können diese Umgebungsvariablen verwenden, um die Dateien und Optionen zu definieren, die Sie am häufigsten verwenden. Zudem können Sie die Befehlszeile verwenden, um bestimmte Dateien und Optionen für bestimmte Zwecke zu definieren.  Die Umgebungsvariablen „CL“ und „\_CL\_“ sind auf 1024 Zeichen \(die Begrenzung für die Befehlszeileneingabe\) beschränkt.  
  
 Sie können nicht die Option „\/D“ zum Definieren eines Symbols verwenden, welches das Gleichheitszeichen \(\=\) verwendet.  Sie können das Nummernzeichen \(\#\) für ein Gleichheitszeichen ersetzen.  Auf diese Weise können Sie die Umgebungsvariablen „CL“ oder „\_CL\_“ zum Definieren von Präprozessorkonstanten mit expliziten Werten verwenden, beispielsweise `/DDEBUG#1` zum Definieren von `DEBUG=1`.  
  
 Zugehörige Informationen finden Sie unter [Festlegen von Umgebungsvariablen](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  
  
## Beispiele  
 Im Folgenden finden Sie ein Beispiel über das Festlegen der Umgebungsvariable „CL“:  
  
```  
SET CL=/Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ  
```  
  
 Wenn diese Umgebungsvariable festgelegt ist, wenn Sie `CL INPUT.C` an der Befehlszeile eingeben, lautet der effektive Befehl:  
  
```  
CL /Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ INPUT.C  
```  
  
 Im folgenden Beispiel wird verursacht, dass ein unformatierter CL\-Befehl die Quelldateien „FILE1.c“ und „FILE2.c“ kompiliert. Anschließend werden die Objektdateien „FILE1.obj“, „FILE2.obj“ und „FILE3.obj“ verknüpft.  
  
```  
SET CL=FILE1.C FILE2.C  
SET _CL_=FILE3.OBJ  
CL  
  
```  
  
 Dies hat den gleichen Effekt wie der Code in der folgenden Befehlszeile:  
  
```  
CL FILE1.C FILE2.C FILE3.OBJ  
```  
  
## Siehe auch  
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)