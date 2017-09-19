---
title: Schwerwiegender Fehler C1083 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1083
dev_langs:
- C++
helpviewer_keywords:
- C1083
ms.assetid: 97e52df3-e79c-4f85-8f1e-bbd1057d55e7
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: bbc5e1f78ca1ea15e65fdd76b7ecd2ea0e195b00
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1083"></a>Schwerwiegender Fehler C1083
Öffnen der Dateityp-Datei 'Datei' nicht möglich: Meldung  
  
 Der Compiler generiert den Fehler C1083, wenn er eine Datei nicht finden kann. Nachstehend finden Sie allgemeine Gründe, warum der Compiler diesen Fehler generiert.  
  
 **Der angegebene Dateiname ist falsch**  
  
 Der Name einer Datei wurde möglicherweise falsch geschrieben werden. Beispiel:  
  
```cpp  
#include <algorithms.h>  
```  
  
 Die von Ihnen gewünschte Datei wird möglicherweise nicht gefunden. Es gibt eine C++-Standardbibliothek-Headerdatei mit dem Namen Algorithmen, die keine Erweiterung .h-Datei. Diese Datei würde mit dieser `include`-Direktive nicht gefunden werden. Überprüfen Sie zur Behebung dieses Problems, ob Sie den richtigen Dateinamen eingegeben haben.  
  
 Bestimmte Header der C-Laufzeitbibliothek befinden sich in einem Unterverzeichnis des Standardincludeverzeichnisses. Wenn Sie beispielsweise "sys\types.h" einbeziehen möchten, müssen Sie den Namen des sys-Unterverzeichnisses in die Includeanweisung einschließen:  
  
 `#include <sys\types.h>`  
  
 **Die Datei wird nicht in den compilersuchpfad einbezogen.**  
  
 Der Compiler kann die Datei anhand der Suchregeln, die in einer `include`- oder `import`-Direktive angegeben wurden, nicht finden. Durch einen in Anführungszeichen eingeschlossenen Headerdateinamen  
  
 `#include "myincludefile.h"`  
  
 wird der Compiler z. B. angewiesen, zuerst in dem Verzeichnis, das die Quelldatei enthält, und dann an anderen Speicherorten nach der Datei zu suchen, die in der Buildumgebung angegeben wurden. Wenn die Anführungszeichen einen absoluten Pfad enthalten, sucht der Compiler nur nach der Datei an diesem Speicherort. Wenn die Anführungszeichen einen relativen Pfad enthalten, sucht der Compiler nach der Datei im Verzeichnis relativ zum Quellverzeichnis. Ist der Name in spitze Klammern eingeschlossen  
  
 `#include <stdio.h>`  
  
 der Compiler folgt einen Suchpfad, der durch die Buildumgebung definiert ist die **/i** -Compileroption verwenden, die **/x** (Compileroption), und die **INCLUDE** -Umgebungsvariablen angegeben. Weitere Informationen, einschließlich spezifische Details über die Suchreihenfolge verwendet, um eine Datei zu suchen, finden Sie unter [#include-Direktive (C/C++)](../../preprocessor/hash-include-directive-c-cpp.md) und [#import-Direktive](../../preprocessor/hash-import-directive-cpp.md).  
  
 Auch wenn Headerdateien im aufgeführt sind **Projektmappen-Explorer** als Teil eines Projekts, die Dateien nur gefunden, durch den Compiler, wenn sie von bezeichnet sind ein `include` oder `import` Richtlinie und sind befindet sich auf einen Verzeichnispfad für die Suche. Für unterschiedliche Buildtypen können unterschiedliche Suchpfade verwendet werden. Die **/x** -Compileroption kann verwendet werden, um Verzeichnisse aus dem Suchpfad für die Includedatei auszuschließen. Dadurch können für verschiedene Builds unterschiedliche Includedateien verwendet werden, die denselben Namen besitzen, sich aber in unterschiedlichen Verzeichnissen befinden. Dies ist eine Alternative zur bedingten Kompilierung mithilfe von Präprozessorbefehlen. Weitere Informationen zu den **/x** -Compileroption verwenden, finden Sie unter [/x (ignorieren Standard Standardincludepfad)](../../build/reference/x-ignore-standard-include-paths.md).  
  
 Beim Aufrufen des Compilers über die Befehlszeile werden Suchpfade oft mithilfe von Umgebungsvariablen angegeben. Wenn von der Suchpfad beschrieben die **INCLUDE** -Umgebungsvariable nicht ordnungsgemäß festgelegt ist, wird ein Fehler C1083 generiert. Weitere Informationen zur Verwendung von Umgebungsvariablen finden Sie unter [wie: Verwenden von Umgebungsvariablen in einem Build](/visualstudio/msbuild/how-to-use-environment-variables-in-a-build).  
  
 Korrigieren Sie zur Behebung dieses Problems den Pfad, den der Compiler für die Suche nach der eingeschlossenen oder importierten Datei verwendet. Für ein neues Projekt werden Standardsuchpfade verwendet. Möglicherweise müssen Sie den Pfad ändern, um ein Verzeichnis für das Projekt hinzuzufügen. Wenn Sie über die Befehlszeile kompilieren, legen Sie die **INCLUDE** -Umgebungsvariablen angegeben oder die **/i** Compileroption, um den Pfad der Datei angeben. Öffnen Sie zur Festlegung des includeverzeichnispfads in Visual Studio des Projekts **Eigenschaftenseiten** Dialogfeld erweitern Sie **Konfigurationseigenschaften** und **VC++-Verzeichnisse**, und bearbeiten Sie dann die **Includeverzeichnisse** Wert. Weitere Informationen zu den Erweiterungen pro Benutzer und pro Projekt Verzeichnisse, die vom Compiler in Visual Studio durchsucht, finden Sie unter [VC++-Verzeichnisse Eigenschaftenseite](../../ide/vcpp-directories-property-page.md). Weitere Informationen zu den **/i** -Compileroption verwenden, finden Sie unter [/i (Zusätzliche Includeverzeichnisse)](../../build/reference/i-additional-include-directories.md).  
  
 **Die falsche Version eines Dateinamens ist enthalten.**  
  
 Ein Fehler C1083 kann auch darauf hinweisen, dass die falsche Version einer Datei verwendet wird. Ein Build kann z. B. die falsche Version einer Datei enthalten, die eine nicht für diesen Build vorgesehene `include`-Direktive für eine Headerdatei aufweist. Wenn die Headerdatei nicht gefunden wird, generiert der Compiler einen Fehler C1083. Dieses Problem kann behoben werden, indem die richtige Datei verwendet wird. Durch Hinzufügen der Headerdatei oder des Verzeichnisses zum Build lässt sich das Problem nicht beheben.  
  
 **Die vorkompilierten Header sind noch nicht vorkompiliert**  
  
 Wenn ein Projekt zur Verwendung vorkompilierter Header konfiguriert ist, müssen die entsprechenden PCH-Dateien erstellt werden, damit Dateien, die den Headerinhalt verwenden, kompiliert werden können. Die Datei "stdafx.cpp" wird z. B. automatisch im Projektverzeichnis für neue MFC-Projekte erstellt. Kompilieren Sie diese Datei zuerst, um die vorkompilierten Headerdateien zu erstellen. (Beim typischen Buildprozessentwurf wird dieser Schritt automatisch ausgeführt.) Weitere Informationen finden Sie unter [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md).  
  
 **Weitere Ursachen**  
  
-   Die Datei verwendet verwalteten Code, aber die Compileroption " **" / CLR "** nicht angegeben wird. Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
-   Die Datei wird mit einer anderen kompiliert **/ analyze** Einstellung als zum Vorkompilieren der Header verwendet wird. (Wenn die Header für ein Projekt vorkompiliert werden, sollten alle verwenden die gleiche **/ analyze** Einstellungen.) Weitere Informationen finden Sie unter [/analyze (Codeanalyse)](../../build/reference/analyze-code-analysis.md).  
  
-   Die Datei, das Verzeichnis oder der Datenträger ist schreibgeschützt.  
  
-   Zugriffsberechtigungen für die Datei oder das Verzeichnis werden nicht gewährt.  
  
-   Es sind nicht genügend Dateihandles vorhanden. Schließen Sie einige Anwendungen, und kompilieren Sie dann erneut. Diese Bedingung ist unter normalen Umständen ungewöhnlich. Sie kann jedoch auftreten, wenn große Projekte auf einem Computer erstellt werden, dessen physischer Speicher beschränkt ist.  
  
 Im folgenden Beispiel wird ein Fehler C1083 generiert.  
  
```  
// C1083.cpp  
// compile with: /c  
#include "test.h"   // C1083 test.h does not exist  
#include "stdio.h"   // OK  
```  
  
 Informationen zum Erstellen von C/C++-Projekten in der IDE oder in der Befehlszeile und Informationen zum Festlegen von Umgebungsvariablen finden Sie [Erstellen eines C/C++-Programms](../../build/building-c-cpp-programs.md).
 
 ## <a name="see-also"></a>Siehe auch
 [MSBuild-Eigenschaften](/visualstudio/msbuild/msbuild-properties)
