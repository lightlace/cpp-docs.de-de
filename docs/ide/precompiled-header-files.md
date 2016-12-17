---
title: "Vorkompilierte Headerdateien"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - ""stdafx.h""
  - "stdafx.h"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "stdafx.h"
  - "PCH-Dateien, Dateibeschreibungen"
  - ".pch-Dateien, Dateibeschreibungen"
  - "Vorkompilierte Headerdateien, Dateibeschreibungen"
  - "stdafx.cpp"
ms.assetid: 8228d87a-5609-41f3-9697-b16094c000e5
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Vorkompilierte Headerdateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Dateien werden dazu verwendet, die vorkompilierte Headerdatei *Projektname.pch* und die vorkompilierte Typendatei „StdAfx.obj“ zu erstellen.  
  
 Diese Dateien befinden sich im Verzeichnis *Projektname*. Im Projektmappen\-Explorer befindet sich „Stdafx.h“ im Ordner „Headerdateien“ und „Stdafx.cpp“ im Ordner „Quelldateien“.  
  
|Dateiname|Beschreibung|  
|---------------|------------------|  
|Stdafx.h|Eine Includedatei für systemspezifische Standardincludedateien und projektspezifische Includedateien, die häufig verwendet, aber nur selten geändert werden.<br /><br /> Sie sollten für keines der \_AFX\_NO\_XXX\-Makros in „stdafx.h“ dessen Definition ändern. Weitere Informationen hierzu finden Sie im Knowledge Base\-Artikel „PRB: Probleme beim Definieren von \_AFX\_NO\_XXX“. Sie finden Knowledge Base\-Artikel in MSDN Library oder unter [http:\/\/support.microsoft.com](http://%20support.microsoft.com/).|  
|Stdafx.cpp|Enthält die Präprozessordirektive `#include "stdafx.h"` und fügt Includedateien für vorkompilierte Typen hinzu. Vorkompilierte Dateien eines beliebigen Typs, einschließlich Headerdateien, sorgen für kürzere Kompilierungszeiten, indem sie die Kompilierung auf die Dateien beschränken, die dies erfordern. Sobald Ihr Projekt erstmalig erstellt wurde, werden Sie feststellen, dass die Buildzeiten nachfolgender Builds aufgrund der vorkompilierten Headerdateien sehr viel kürzer sind.|  
  
## Siehe auch  
 [Für Visual C\+\+\-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Gewusst wie: Festlegen von Projekteigenschaften mit Eigenschaftenseiten](../misc/how-to-specify-project-properties-with-property-pages.md)