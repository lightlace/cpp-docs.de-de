---
title: Vorkompilierte Headerdateien | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: stdafx.h
dev_langs: C++
helpviewer_keywords:
- stdafx.h
- PCH files, file descriptions
- .pch files, file descriptions
- precompiled header files, file descriptions
- stdafx.cpp
ms.assetid: 8228d87a-5609-41f3-9697-b16094c000e5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1208b000f57397764277cc0a43e223f7c781a06e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="precompiled-header-files"></a>Vorkompilierte Headerdateien
Diese Dateien werden dazu verwendet, die vorkompilierte Headerdatei *Projektname.pch*und die vorkompilierte Typendatei „StdAfx.obj“ zu erstellen.  
  
 Diese Dateien befinden sich im Verzeichnis *Projektname* . Im Projektmappen-Explorer befindet sich „Stdafx.h“ im Ordner „Headerdateien“ und „Stdafx.cpp“ im Ordner „Quelldateien“.  
  
|Dateiname|Beschreibung|  
|---------------|-----------------|  
|stdafx.h|Eine Includedatei für systemspezifische Standardincludedateien und projektspezifische Includedateien, die häufig verwendet, aber nur selten geändert werden.<br /><br /> Sie sollten für keines der _AFX_NO_XXX-Makros in „stdafx.h“ dessen Definition ändern. Weitere Informationen hierzu finden Sie im Knowledge Base-Artikel „PRB: Probleme beim Definieren von _AFX_NO_XXX“. Sie finden Knowledge Base-Artikel in MSDN Library oder unter [http://support.microsoft.com](http://%20support.microsoft.com/).|  
|stdafx.cpp|Enthält die Präprozessordirektive `#include "stdafx.h"` und fügt Includedateien für vorkompilierte Typen hinzu. Vorkompilierte Dateien eines beliebigen Typs, einschließlich Headerdateien, sorgen für kürzere Kompilierungszeiten, indem sie die Kompilierung auf die Dateien beschränken, die dies erfordern. Sobald Ihr Projekt erstmalig erstellt wurde, werden Sie feststellen, dass die Buildzeiten nachfolgender Builds aufgrund der vorkompilierten Headerdateien sehr viel kürzer sind.|  
  
## <a name="see-also"></a>Siehe auch  
 [Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)