---
title: 'Ressourcencompiler: Schwerwiegender Fehler RC1015 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC1015
dev_langs: C++
helpviewer_keywords: RC1015
ms.assetid: 23f187e1-5538-40b5-9042-edd2888f55c2
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 666221cf5c3e812cd856271ea97cf4966383ec20
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rc1015"></a>Ressourcencompiler: Schwerwiegender Fehler RC1015
Includedatei 'Dateiname' kann nicht geöffnet werden  
  
 Die angegebene Includedatei ist nicht vorhanden, konnte nicht geöffnet werden oder wurde nicht gefunden.  
  
 Stellen Sie sicher, dass die Umgebungseinstellungen gültig sind und der richtige Pfad für die Datei angegeben wurde. Stellen Sie sicher, dass genügend Dateihandles Ressourcencompiler zur Verfügung stehen. Wenn die Datei auf einem Netzlaufwerk befindet, stellen Sie sicher, dass Sie über Berechtigungen zum Öffnen der Datei verfügen.  
  
 RC1015 kann auftreten, auch wenn die Include-Datei vorhanden, in ein Verzeichnis angegeben ist, wie ein zusätzliches Includeverzeichnis in den Konfigurationseigenschaften -> Ressourcen -> Eigenschaftenseite Allgemein; Geben Sie den vollständigen Pfad zu der Include-Datei.  
  
 Weitere Informationen finden Sie im Knowledge Base-Artikel Q326987: RC1015 Fehler beim Verwenden von Ressource Ansicht Wenn Includepfad ist zu lang.