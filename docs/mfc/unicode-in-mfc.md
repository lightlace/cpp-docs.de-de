---
title: Unicode in MFC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- wide characters, Unicode
- Unicode [MFC], MFC
- wide characters, encoding
- strings [MFC], Unicode
- Unicode [MFC], enabling
ms.assetid: 1002004b-4113-4380-bf63-e1570934b793
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2c1a104ffc30a7463d640f63d26f7a80faad333b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="unicode-in-mfc"></a>Unicode in MFC
MFC unterstützt den Unicode-Standard zum Codieren von Breitzeichen unter Windows NT, Windows 2000 und Windows XP-Plattformen. Unicode-Anwendungen können nicht auf Windows 98-Plattformen ausgeführt.  
  
 Die Unicode-Versionen der MFC-Bibliotheken sind im folgenden beschrieben:  
  
### <a name="static-link-libraries"></a>Static Link Libraries  
  
|Release|Debug|Beschreibung|  
|-------------|-----------|-----------------|  
|UAFXCW.lib, PDB-Datei|UAFXCWD.lib, PDB-Datei|Unicode-MFC-Bibliothek für statische Verknüpfung|  
  
### <a name="dynamic-link-libraries"></a>Dynamic Link Libraries  
  
|Version|Debug|Beschreibung|  
|-------------|-----------|-----------------|  
|MFC100U.lib, .dbg, "def", DLL, .map, PDB-Datei, .prf|MFC100UD.lib "," def ",".dll ",".map "," PDB-Datei|Unicode MFC-Importbibliothek (siehe Hinweise unten Erläuterung der Dateierweiterungen)|  
|MFCS100U.lib, PDB-Datei|MFCS100UD.lib, PDB-Datei|Unicode MFC-Importbibliothek mit Code, die statisch mit einer Anwendung oder DLL verknüpft werden muss|  
  
 **Dateitypen**  
  
-   Import-Bibliotheksdateien haben die Erweiterung (.lib).  
  
-   Dynamic Link Library-Dateien haben die Erweiterung (.dll).  
  
-   Moduldefinitionsdateien (.def) sind Textdateien, die zum Definieren einer .exe oder .dll-Anweisungen enthalten.  
  
-   Zuordnungsdateien ()-Dateien sind Textdateien, die Informationen, die der Linker verwendet werden enthalten, wenn ein Programm verknüpfen.  
  
-   Bibliotheksdateien (.lib) werden in Verbindung mit der DLL-Versionen von MFC verwendet. Diese Dateien enthalten Code, der statisch mit der Anwendung oder DLL verknüpft werden muss.  
  
-   Programmdatenbankdateien (PDB) enthält Debug- und Statusinformationen.  
  
-   (.Dbg)-Debugdateien enthalten Informationen (COFF FPO und Codeansichtsinformationen), die der Visual C++-Debugger verwendet.  
  
 Ausführliche Informationen zu Namenskonventionen, finden Sie unter [Bibliotheks-Benennungskonventionen](../mfc/library-naming-conventions.md).  
  
 Informationen zur Verwendung von Unicode mit MFC finden Sie unter [Zeichenfolgen: Unicode- und Multibyte-Zeichensätzen (MBCS)-Unterstützung](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)   
 [Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)

