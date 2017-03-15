---
title: "Linkertoolwarnung LNK4070 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4070"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4070"
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Linkertoolwarnung LNK4070
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Direktive \/OUT:Dateiname in .EXP weicht vom Ausgabedateinamen 'Dateiname' ab; Direktive wird ignoriert  
  
 Der `filename`, der beim Erstellen der EXP\-Datei in der Anweisung [NAME](../../build/reference/name-c-cpp.md) oder [LIBRARY](../../build/reference/library.md) angegeben wurde, stimmt nicht mit dem `filename` für die Ausgabe überein, der entweder standardmäßig übernommen oder mit der [\/OUT](../../build/reference/out-output-file-name.md)\-Option festgelegt wurde.  
  
 Diese Warnung wird angezeigt, wenn Sie den Namen einer Ausgabedatei in der Entwicklungsumgebung ändern und die DEF\-Datei des Projekts nicht aktualisiert wurde.  Aktualisieren Sie die DEF\-Datei manuell, um diese Warnung zu vermeiden.  
  
 Bei einem Clientprogramm, das die resultierende DLL verwendet, können Probleme auftreten.