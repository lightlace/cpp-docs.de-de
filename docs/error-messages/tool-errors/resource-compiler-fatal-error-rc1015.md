---
title: "Ressourcencompiler: Schwerwiegender Fehler RC1015 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC1015"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1015"
ms.assetid: 23f187e1-5538-40b5-9042-edd2888f55c2
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ressourcencompiler: Schwerwiegender Fehler RC1015
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Includedatei 'Dateiname' kann nicht geöffnet werden  
  
 Die angegebene Includedatei ist nicht vorhanden, konnte nicht geöffnet oder konnte nicht gefunden werden.  
  
 Stellen Sie sicher, dass die Umgebungseinstellungen zulässig sind und der richtige Pfad für die Datei angegeben ist.  Stellen Sie sicher, dass dem Ressourcencompiler genügend Dateihandles zur Verfügung stehen.  Wenn sich die Datei auf einem Netzlaufwerk befindet, stellen Sie sicher, dass Sie über die Berechtigung verfügen, die Datei zu öffnen.  
  
 RC1015 kann auftreten, wenn die Includedatei in einem Verzeichnis befindet, das als zusätzliches Includeverzeichnis in unter Konfigurationseigenschaften angegeben \-\> Ressourcen \-\>\-Eigenschaftenseite Allgemein; Geben Sie den vollständigen Pfad zur Includedatei an.  
  
 Weitere Informationen finden Sie im Knowledge Base\-Artikel Q326987: "RC1015 Error When Using Resource View If the Include Path is Too Long" \(nur auf Englisch verfügbar\).