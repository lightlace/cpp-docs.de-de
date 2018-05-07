---
title: 'Ressourcencompiler: Schwerwiegender Fehler RC1015 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC1015
dev_langs:
- C++
helpviewer_keywords:
- RC1015
ms.assetid: 23f187e1-5538-40b5-9042-edd2888f55c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b7744242e44ecfc72ee57ab979969ad81b209e57
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-fatal-error-rc1015"></a>Ressourcencompiler: Schwerwiegender Fehler RC1015
Includedatei 'Dateiname' kann nicht geöffnet werden  
  
 Die angegebene Includedatei ist nicht vorhanden, konnte nicht geöffnet werden oder wurde nicht gefunden.  
  
 Stellen Sie sicher, dass die Umgebungseinstellungen gültig sind und der richtige Pfad für die Datei angegeben wurde. Stellen Sie sicher, dass genügend Dateihandles Ressourcencompiler zur Verfügung stehen. Wenn die Datei auf einem Netzlaufwerk befindet, stellen Sie sicher, dass Sie über Berechtigungen zum Öffnen der Datei verfügen.  
  
 RC1015 kann auftreten, auch wenn die Include-Datei vorhanden, in ein Verzeichnis angegeben ist, wie ein zusätzliches Includeverzeichnis in den Konfigurationseigenschaften -> Ressourcen -> Eigenschaftenseite Allgemein; Geben Sie den vollständigen Pfad zu der Include-Datei.  
  
 Weitere Informationen finden Sie im Knowledge Base-Artikel Q326987: RC1015 Fehler beim Verwenden von Ressource Ansicht Wenn Includepfad ist zu lang.