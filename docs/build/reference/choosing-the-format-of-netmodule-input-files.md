---
title: Auswählen des Formats von NETMODULE-Dateien Eingabe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 4653d1bd-300f-4083-86f5-d1a06f44e61c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62575d3e816bdc10587e7a4c9cebcea735329ec1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="choosing-the-format-of-netmodule-input-files"></a>Auswählen des Formats von .netmodule-Eingabedateien
Eine MSIL-OBJ-Datei (kompiliert mit ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md)) kann auch als eine NETMODULE-Datei verwendet werden.  OBJ-Dateien werden Metadaten und systemeigene Symbole enthalten.  NETMODULE-Dateien enthalten nur Metadaten.  
  
 Sie können eine MSIL-OBJ-Datei an andere Visual Studio-Compiler übergeben, über die/addmodule-Compileroption (aber beachten Sie, dass die OBJ-Datei die resultierende Assembly wird und mit der Assembly ausgeliefert werden muss).  Beispielsweise haben in Visual c# und Visual Basic/addmodule-Compileroption.  
  
> [!NOTE]
>  In den meisten Fällen müssen Sie an den Linker die OBJ-Datei aus der Kompilierung übergeben, die das Modul .net erstellt.  Eine DLL- oder NETMODULE-MSIL-Modul-Datei an dem Linker übergeben kann dazu führen, dass LNK1107.  
  
 OBJ-Dateien sowie ihre zugeordneten h-Dateien, die Sie, über verweisen #include in der Quelle, C++-Anwendungen für die systemeigenen Typen im Modul nutzen können, dagegen in eine NETMODULE-Datei nur die verwalteten Typen, die von einer C++-Anwendung genutzt werden können.  Wenn Sie versuchen, eine OBJ-Datei übergeben #using, Informationen zu systemeigenen Typen nicht zur Verfügung; #include Sie stattdessen die OBJ-Datei .h-Datei.  
  
 Andere Visual Studio-Compiler können nur verwaltete Typen aus einem Modul nutzen.  
  
 Verwenden Sie Folgendes, um zu bestimmen, ob Sie eine NETMODULE-Datei oder eine OBJ-Datei als Moduleingabe an den Visual C++-Linker verwenden müssen:  
  
-   Wenn Sie mit einem Visual Studio-Compiler als Visual C++ erstellen, erstellen Sie eine NETMODULE, und verwenden Sie die NETMODULE-Datei als Eingabe an den Linker.  
  
-   Wenn Sie Visual C++-Compiler verwenden werden, um zu erzeugen, Module und wenn die Module verwendet wird, um etwas anderes als eine Bibliothek zu erstellen, verwenden Sie die OBJ-Dateien, die vom Compiler als Moduleingabe an den Linker erstellt; Verwenden Sie nicht die NETMODULE-Datei als Eingabe.  
  
-   Wenn Ihre Module Erstellen einer systemeigenen (keine verwaltete)-Bibliothek verwendet werden soll, verwenden Sie die OBJ-Dateien als Moduleingabe an den Linker und generieren Sie eine LIB-Bibliotheksdatei.  
  
-   Wenn Ihre Module verwendet werden, um eine verwaltete Bibliothek zu erstellen, und wenn alle Moduleingabe an den Linker überprüfbar sind (erstellt mit/clr: safe), verwenden Sie die OBJ-Dateien als Moduleingabe an den Linker, und erstellen Sie eine DLL-Datei (Assembly) oder die Bibliotheksdatei NETMODULE-Datei (Modul).  
  
-   Wenn Ihre Module verwendet werden, um eine verwaltete Bibliothek zu erstellen und eine oder mehrere Module Eingabe an den Linker mit nur "/ CLR" erzeugt werden, verwenden Sie die OBJ-Dateien als Moduleingabe an den Linker und generiert eine DLL-Datei (Assembly).  Wenn verwalteter Typen aus der Bibliothek und gegebenenfalls auch C++-Anwendungen nutzen die systemeigenen Typen in der Bibliothek verfügbar gemacht werden sollen, wird Ihrer Bibliothek aus der OBJ-Dateien für die Bibliotheken für die komponentenverwaltung bestehen (Sie werden auch die h-Dateien für jedes Modul versenden möchten Damit sie mit verwiesen werden können #include aus Quellcode).  
  
## <a name="see-also"></a>Siehe auch  
 [.NETMODULE-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md)