---
title: "Schwerwiegender Fehler C1010 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1010"
ms.assetid: dfd035f1-a7a2-40bc-bc92-dc4d7f456767
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Schwerwiegender Fehler C1010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unerwartetes Dateiende bei der Suche nach vorkompilierter HeaderdateiMöglicherweise ist "\#include name" im Quellcode nicht vorhanden.  
  
 Eine mit [\/Yu](../../build/reference/yu-use-precompiled-header-file.md) angegebene Includedatei ist nicht in der Quelldatei aufgelistet.  In der Standardeinstellung ist diese Option in den meisten Visual C\+\+\-Projekttypen aktiviert, und "stdafx.h" ist standardmäßig die durch diese Option angegebene Includedatei.  
  
 Verwenden Sie in der Visual Studio\-Umgebung eine der folgenden Methoden, um diesen Fehler zu beheben:  
  
-   Wenn in dem Projekt keine vorkompilierten Header verwendet werden, legen Sie die **Vorkompilierten Header erstellen\/verwenden**\-Eigenschaft für die Quelldateien auf **Vorkompilierte Header nicht verwenden** fest.  Gehen Sie folgendermaßen vor, um diese Compileroption festzulegen:  
  
    1.  Klicken Sie im Bereich Projektmappen\-Explorer des Projekts mit der rechten Maustaste auf den Projektnamen, und klicken Sie anschließend auf **Eigenschaften**.  
  
    2.  Klicken Sie im linken Bereich auf den Ordner **C\/C\+\+**.  
  
    3.  Klicken Sie auf den Knoten **Vorkompilierte Header**.  
  
    4.  Klicken Sie im rechten Bereich auf **Vorkompilierten Header erstellen\/verwenden**, und klicken Sie dann **Vorkompilierte Header nicht verwenden**.  
  
-   Vergewissern Sie sich, dass Sie die Headerdatei für das aktuelle Projekt \(standardmäßig stdafx.h\) nicht versehentlich gelöscht, umbenannt oder entfernt haben.  Diese Datei muss mithilfe von **\#include "stdafx.h"** vor jedem anderen Code in den Quelldateien eingebunden werden. \(Diese Headerdatei wird als **PHC durch Datei erstellen\/verwenden**\-Projekteigenschaft angegeben.\)