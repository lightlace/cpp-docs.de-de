---
title: Compilergesteuerte Linkoptionen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: link
dev_langs: C++
helpviewer_keywords:
- LINK tool [C++], compiler-controlled options
- linker [C++], CL compiler control
- linking [C++], affected by CL features
- cl.exe compiler [C++], features that affect linking
- cl.exe compiler [C++], controlling linker
ms.assetid: e4c03896-c99c-4599-8502-e0f4bebe69d0
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a0d73d46d17e14d5ce55a171887e693c425765ce
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-controlled-link-options"></a>Compiler-Controlled LINK Options
CL-Compiler ruft automatisch LINK, es sei denn, Sie die Option/c angeben. CL stellt eine gewisse Kontrolle über den Linker über Befehlszeilenoptionen und Argumenten bereit. In der folgenden Tabelle werden die Funktionen in der Berechnungsliste, die verknüpfen beeinflussen, zusammengefasst.  
  
|CL-Spezifikation|CL-Aktion, die Verknüpfung wirkt sich auf|  
|----------------------|---------------------------------|  
|Eine beliebige Dateinamenerweiterung als c, .cxx, .cpp oder DEF|Übergibt einen Dateinamen als Eingabe an LINK|  
|*FileName*DEF|/ DEF übergibt:*Filename*DEF|  
|/ F*Anzahl*|Übergibt/Stack:*Anzahl*|  
|/ Fd*Dateiname*|Übergibt/PDB:*Dateiname*|  
|/ FE*Dateiname*|Übergibt/OUT:*Dateiname*|  
|/ FM*Dateiname*|Übergibt/Map:*Dateiname*|  
|/Gy|Erstellt Paketfunktionen (COMDATs); Aktiviert Funktionslevel-Linking|  
|/LD|Übergibt die/DLL|  
|/LDd|Übergibt die/DLL|  
|/link|Übergibt den Rest der Befehlszeile an LINK|  
|/ MD oder/MT|Wird einen Standard-Bibliotheksnamen in der OBJ-Datei|  
|/ MDd oder/MTd|Platziert einen Standard-Bibliotheksnamen in der OBJ-Datei an. Definiert das Symbol **_DEBUG**|  
|/nologo|/ Nologo übergibt|  
|"/ Zd"|Übergibt "/ Debug"|  
|/ Zi oder "/ Z7"|Übergibt "/ Debug"|  
|/Zl|Lässt die Standard-Bibliotheksnamen aus der OBJ-Datei|  
  
 Weitere Informationen finden Sie unter [Compileroptionen](../../build/reference/compiler-options.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)