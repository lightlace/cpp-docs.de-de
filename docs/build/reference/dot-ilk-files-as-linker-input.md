---
title: "ILK-Dateien als Eingabe f&#252;r den Linker"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".ilk-Dateien"
  - "ILK-Dateien"
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# ILK-Dateien als Eingabe f&#252;r den Linker
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Beim inkrementellen Verknüpfen aktualisiert LINK die ILK\-Statusdatei, die während der ersten inkrementellen Verknüpfung erstellt wurde.  Diese Datei hat denselben Basisnamen wie die EXE\- oder DLL\-Datei und verfügt über die Erweiterung **.ilk**.  Bei nachfolgenden inkrementellen Verknüpfungsvorgängen aktualisiert **LINK** die ILK\-Datei.  Wenn sie fehlt, führt **LINK** einen vollständigen Verknüpfungsvorgang durch und erstellt eine neue ILK\-Datei.  Wenn die ILK\-Datei nicht verwendet werden kann, führt **LINK** einen nicht inkrementellen Verknüpfungsvorgang durch.  Weitere Einzelheiten über inkrementelles Verknüpfen finden Sie unter der Option [\/INCREMENTAL \(Inkrementell verknüpfen\)](../../build/reference/incremental-link-incrementally.md).  
  
## Siehe auch  
 [LINK\-Eingabedateien](../../build/reference/link-input-files.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)