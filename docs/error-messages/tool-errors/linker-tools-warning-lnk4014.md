---
title: "Linkertoolwarnung LNK4014"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4014"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4014"
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolwarnung LNK4014
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Memberobjekt "Objektname" nicht gefunden  
  
 LIB konnte `objectname` in der Bibliothek nicht finden.  
  
 Für die Optionen **\/REMOVE** und **\/EXTRACT** ist der vollständige Name des Memberobjekts erforderlich, das gelöscht oder in eine Datei kopiert werden soll.  Der vollständige Name beinhaltet den Pfad der ursprünglichen Objektdatei.  Um die vollständigen Namen von Memberobjekten in einer Bibliothek anzuzeigen, verwenden Sie **DUMPBIN** [\/ARCHIVEMEMBERS](../../build/reference/archivemembers.md) oder **LIB** [\/LIST](../../build/reference/managing-a-library.md).