---
title: "Binden von Importen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAY:NOBIND (Linkeroption)"
  - "DELAY:NOBIND (Linkeroption)"
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Binden von Importen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Standardmäßig wird vom Linker eine bindungsfähige Importadressentabelle für die verzögert geladene DLL erstellt.  Wenn die DLL gebunden ist, versucht die Hilfsfunktion, die Bindungsinformation zu verwenden, anstatt für jeden verwiesenen Import **GetProcAddress** aufzurufen.  Wenn der Timestamp oder die bevorzugte Adresse nicht mit dem Timestamp bzw. der Adresse der geladenen DLL übereinstimmt, wird von der Hilfsfunktion angenommen, dass die gebundene Importadressentabelle \(IAT\) veraltet ist, und die Verarbeitung wird so fortgesetzt, als ob sie nicht vorhanden wäre.  
  
 Wenn nicht beabsichtigt wird, die verzögert geladenen Importe der DLL zu binden, kann durch Angabe von [\/delay](../../build/reference/delay-delay-load-import-settings.md):nobind in der Befehlszeile des Linkers verhindert werden, dass die gebundene Importadressentabelle generiert wird und Platz in der Abbilddatei beansprucht.  
  
## Siehe auch  
 [Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)