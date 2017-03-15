---
title: "Linkertoolfehler LNK1188 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1188"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1188"
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Linkertoolfehler LNK1188
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

BADFIXUPSECTION:: Ungültiges Fixup\-Ziel 'Symbol'; mögliche Null\-Abschnittslänge  
  
 Für das Ziel einer Umsetzung war bei einem VxD\-Link kein Abschnitt verfügbar.  Mit \(einer älteren Version von\) LINK386 wurde u. U. ein \(von einer MASM GROUP\-Direktive erstellter\) OMF GROUP\-Datensatz dazu verwendet, den Abschnitt mit der Länge 0 mit einem anderen Abschnitt zu kombinieren, der nicht die Länge 0 besitzt.  Die GROUP\-Direktive und Abschnitte mit der Länge 0 werden vom COFF\-Format nicht unterstützt.  Dieser Fehler kann auftreten, wenn dieser OMF\-Objekttyp durch LINK automatisch in COFF konvertiert wird.