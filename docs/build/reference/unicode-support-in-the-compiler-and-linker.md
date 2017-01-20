---
title: "Unicode-Unterst&#252;tzung im Compiler und Linker"
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
  - "VC.Project.VCLinkerTool.UseUnicodeResponseFiles"
  - "VC.Project.VCLibrarianTool.UseUnicodeResponseFiles"
  - "VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles"
  - "VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unicode, Visual C++"
ms.assetid: acc1d322-56b9-4696-a30e-2af891a4e288
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Unicode-Unterst&#252;tzung im Compiler und Linker
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird die Unicode\-Unterstützung der Visual C\+\+\-Buildtools beschrieben.  
  
 Dateinamen  
 In der Befehlszeile oder in Compilerdirektiven \(wie \#include\) angegebene Dateinamen können jetzt Unicode\-Zeichen enthalten.  
  
 Quellcodedateien  
 Unicode\-Zeichen werden jetzt in Bezeichnern, Makros, Zeichenfolgen und Zeichenliteralen sowie in Kommentaren unterstützt.  Universelle Zeichennamen werden nun ebenfalls unterstützt.  
  
 Unicode kann in den folgenden Codierungen in eine Quellcodedatei eingegeben werden:  
  
-   UTF\-16\-Little\-Endian mit oder ohne Bytereihenfolgemarkierung \(BOM\)  
  
-   UTF\-16\-Big\-Endian mit oder ohne BOM  
  
-   UTF\-8 mit BOM  
  
 Ausgabe  
 Bei der Kompilierung werden vom Compiler Diagnosemeldungen an die Konsole in UTF\-16 ausgegeben.  Welche Zeichen auf Ihrer Konsole angezeigt werden können, ist von den Eigenschaften des Konsolenfensters abhängig.  Die in eine Datei umgeleitete Compilerausgabe entspricht der aktuellen ANSI\-Konsolencodepage.  
  
 Antwortdateien für den Linker und DEF\-Dateien  
 Antwortdateien und DEF\-Dateien können entweder das Format UTF\-16 mit einer Bytereihenfolgenmarkierung oder ANSI haben.  Zuvor wurde nur ANSI unterstützt.  
  
 ASM\- und COD\-Dumps  
 ASM\- und COD\-Dumps müssen standardmäßig in ANSI sein, damit die Kompatibilität mit MASM gewährleistet ist.  Verwenden Sie \/FAu für die Ausgabe in UTF\-8.  Beachten Sie, dass bei Angabe von \/FAs die vermischte Quelle einfach direkt ausgegeben wird und verstümmelt aussehen kann, z. B. wenn der Quellcode UTF\-8 ist und Sie nicht \/FAsu angegeben haben.  
  
 Sie können Unicode\-Dateinamen in der Entwicklungsumgebung aktivieren \(siehe [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md)\), indem Sie das entsprechende Tool und die Eigenschaft **Unicode\-Antwortdateien aktivieren** auswählen, die standardmäßig aktiviert ist.  Ein Grund zum Ändern dieser Standardeinstellung könnte darin bestehen, dass Sie Ihre Entwicklungsumgebung für die Verwendung eines Compilers ändern, der nicht über Unicode\-Unterstützung verfügt.  
  
## Siehe auch  
 [Erstellen über die Befehlszeile](../../build/building-on-the-command-line.md)