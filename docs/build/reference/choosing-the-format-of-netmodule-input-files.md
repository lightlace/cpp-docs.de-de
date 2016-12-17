---
title: "Ausw&#228;hlen des Formats von .netmodule-Eingabedateien"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 4653d1bd-300f-4083-86f5-d1a06f44e61c
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Ausw&#228;hlen des Formats von .netmodule-Eingabedateien
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine MSIL\-OBJ\-Datei \(kompiliert mit [\/clr](../../build/reference/clr-common-language-runtime-compilation.md)\) kann als .netmodule\-Datei auch verwendet werden.  OBJ\-Dateien enthalten Metadaten und systemeigene Symbole.  .netmodules enthalten nur Metadaten.  
  
 Sie können eine MSIL\-OBJ\-Datei über die Compileroption \/addmodule an einen beliebigen anderen Visual Studio\-Compiler übergeben. \(Beachten Sie jedoch, dass die OBJ\-Datei Teil der erstellten Assembly wird und zusammen mit dieser versendet werden muss.\)  Zum Beispiel verfügen Visual C\# und Visual Basic über die Compileroption \/addmodule.  
  
> [!NOTE]
>  In den meisten Fällen müssen Sie für den Linker die OBJ\-Datei von der Kompilierung übergeben, die das Modul .net\- erstellt hat.  Eine Ausnahme hierzu besteht, wenn .netmodule mit [\/clr:pure](../../build/reference/clr-common-language-runtime-compilation.md) erstellt wurde.  Das Übergeben einer DLL\- oder der Moduldatei .netmodules MSIL den Linker kann LNK1107.  
  
 OBJ\-Dateien, zusammen mit ihren zugeordneten H\-Dateien, die Sie für \#include in Quelle verweisen, können C\+\+\-Anwendungen, das systemeigene nutzen Typen in das Modul, während in einer .netmodule\-Datei, nur die verwalteten Typen durch einer C\+\+\-Anwendung genutzt werden können.  Beim Übergeben einer OBJ\-Datei mit \#using sind keine Informationen zu systemeigenen Typen verfügbar. Fügen Sie stattdessen mit \#include die H\-Datei der OBJ\-Datei ein.  
  
 Andere Visual Studio\-Compiler können nur verwaltete Typen eines Moduls verwenden.  
  
 Verwenden Sie das folgende, um festzustellen, ob Sie .netmodule verwenden müssen, oder eine OBJ\-Datei als Modul zu Visual C\+\+ dem Linker eingab:  
  
-   Wenn Sie einem Visual Studio\-Compiler als Visual C\+\+ erstellen, erzeugen .netmodule und verwenden Sie .netmodule, wie als Eingabe für den Linker.  
  
-   Wenn Sie den Visual C\+\+\-Compiler verwenden, Module zu erzeugen und wenn Module verwendet werden, um ein anderes Ergebnis als eine Bibliothek zu erstellen, verwenden Sie die OBJ\-Dateien, die vom Compiler als Modul erstellt werden, das den Linker eingegeben wird; verwenden Sie die .netmodule\-Datei nicht, als Eingabe.  
  
-   Wenn die Module zur Erstellung einer systemeigenen \(und nicht einer verwalteten\) Bibliothek verwendet werden, verwenden Sie die OBJ\-Dateien als Moduleingabe in den Linker, und erstellen Sie eine LIB\-Bibliotheksdatei.  
  
-   Wenn die Module verwendet werden, um eine verwaltete Bibliothek zu erstellen und wenn alle Moduleingabe den Linker \(erstellt mit \/clr:safe\) überprüfbar ist, Verwendungsobj\-dateien als Moduleingabe den Linker und eine Bibliotheksdatei .dll \(Assembly\) oder .netmodules \(Modul\) generieren.  
  
-   Wenn die Module verwendet werden, um eine verwaltete Bibliothek zu erstellen und wenn alle Moduleingabe den Linker mit \/clr:pure oder \/clr:safe, Verwendungsobj\-dateien als Moduleingabe den Linker und eine DLL\-Datei \(Assembly\) zu generieren oder .netmodule \(Modul\) erzeugten wenn Sie nur verwaltete Typen von der Bibliothek verfügbar machen möchten.  Wenn Sie verwaltete Typen aus der Bibliothek verfügbar machen möchten und die systemeigenen Typen in der Bibliothek außerdem von C\+\+\-Anwendungen verwendet werden sollen, besteht ihre Bibliothek aus den OBJ\-Dateien für die Komponentenmodule der Bibliothek \(wahrscheinlich möchten Sie auch die H\-Dateien für jedes Modul versenden, sodass diese mit \#include vom Quellcode referenziert werden können\).  
  
-   Wenn die Module zur Erstellung einer verwalteten Bibliothek verwendet werden und wenn mindestens ein Eingabemodul für den Linker ausschließlich mit \/clr erstellt wird, verwenden Sie OBJ\-Dateien als Moduleingabe in den Linker, und erstellen Sie eine DLL\-Datei \(Assembly\).  Wenn Sie verwaltete Typen aus der Bibliothek verfügbar machen möchten und die systemeigenen Typen in der Bibliothek außerdem von C\+\+\-Anwendungen verwendet werden sollen, besteht ihre Bibliothek aus den OBJ\-Dateien für die Komponentenmodule der Bibliothek \(wahrscheinlich möchten Sie auch die H\-Dateien für jedes Modul versenden, sodass diese mit \#include vom Quellcode referenziert werden können\).  
  
## Siehe auch  
 [.NETMODULE\-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md)