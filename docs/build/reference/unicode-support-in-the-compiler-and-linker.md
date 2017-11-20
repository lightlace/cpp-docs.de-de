---
title: "Unicode-Unterstützung im Compiler und Linker | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.UseUnicodeResponseFiles
- VC.Project.VCLibrarianTool.UseUnicodeResponseFiles
- VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles
- VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles
dev_langs: C++
helpviewer_keywords: Unicode, Visual C++
ms.assetid: acc1d322-56b9-4696-a30e-2af891a4e288
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 15fefc4cc44edfd67bd8ba89ab68c6965c8639a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="unicode-support-in-the-compiler-and-linker"></a>Unicode-Unterstützung im Compiler und Linker
In diesem Thema wird die Unicode-Unterstützung der Visual C++-Buildtools beschrieben.  
  
 Dateinamen  
 In der Befehlszeile oder in Compilerdirektiven (wie #include) angegebene Dateinamen können jetzt Unicode-Zeichen enthalten.  
  
 Quellcodedateien  
 Unicode-Zeichen werden jetzt in Bezeichnern, Makros, Zeichenfolgen und Zeichenliteralen sowie in Kommentaren unterstützt.  Universelle Zeichennamen werden nun ebenfalls unterstützt.  
  
 Unicode kann in den folgenden Codierungen in eine Quellcodedatei eingegeben werden:  
  
-   UTF-16-Little-Endian mit oder ohne Bytereihenfolgemarkierung (BOM)  
  
-   UTF-16-Big-Endian mit oder ohne BOM  
  
-   UTF-8 mit BOM  
  
 Ausgabe  
 Bei der Kompilierung werden vom Compiler Diagnosemeldungen an die Konsole in UTF-16 ausgegeben.  Welche Zeichen auf Ihrer Konsole angezeigt werden können, ist von den Eigenschaften des Konsolenfensters abhängig.  Die in eine Datei umgeleitete Compilerausgabe entspricht der aktuellen ANSI-Konsolencodepage.  
  
 Antwortdateien für den Linker und DEF-Dateien  
 Antwortdateien und DEF-Dateien können entweder das Format UTF-16 mit einer Bytereihenfolgenmarkierung oder ANSI haben.  Zuvor wurde nur ANSI unterstützt.  
  
 ASM- und COD-Dumps  
 ASM- und COD-Dumps müssen standardmäßig in ANSI sein, damit die Kompatibilität mit MASM gewährleistet ist.  Verwenden Sie /FAu für die Ausgabe in UTF-8.  Beachten Sie, dass bei Angabe von /FAs die vermischte Quelle einfach direkt ausgegeben wird und verstümmelt aussehen kann, z. B. wenn der Quellcode UTF-8 ist und Sie nicht /FAsu angegeben haben.  
  
 Sie können Unicode-Dateinamen in der Entwicklungsumgebung (finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md)) durch Auswählen des geeigneten Tools und Auswählen der **Aktivieren von Unicode-Antwortdateien** -Eigenschaft, die ist standardmäßig aktiviert. Ein Grund zum Ändern dieser Standardeinstellung könnte darin bestehen, dass Sie Ihre Entwicklungsumgebung für die Verwendung eines Compilers ändern, der nicht über Unicode-Unterstützung verfügt.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von C/C++-Code in der Befehlszeile](../../build/building-on-the-command-line.md)