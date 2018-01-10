---
title: Schwerwiegender Fehler C1902 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1902
dev_langs: C++
helpviewer_keywords: C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4e5f6c22ea848a49a12cc85508fd80a4cfcb90e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1902"></a>Schwerwiegender Fehler C1902
Fehlende Übereinstimmung Programm Datenbank-Manager; Bitte überprüfen Sie die installation  
  
Erstellt eine Programmdatenbankdatei (.pdb) wurde mit einer neueren Version von Mspdb*XXX*DLL demjenigen, der Compiler auf Ihrem System gefunden. Dieser Fehler gibt normalerweise an, dass mspdbsrv.exe oder mspdbcore.dll fehlen oder andere Versionen als Mspdb*XXX*DLL. (Die *XXX* Platzhalter in der Mspdb*XXX*.dll-Datei ändert sich mit jeder Produktversion. Beispielsweise wird in Visual Studio 2015 ist der Dateiname mspdb140.dll.)  
  
Stellen Sie sicher übereinstimmende Versionen von mspdbsrv.exe, mspdbcore.dll und Mspdb*XXX*DLL-Datei auf Ihrem System installiert sind. Stellen Sie sicher, dass nicht übereinstimmende Versionen nicht in das Verzeichnis kopiert wurden, die der Compiler und Link-Tools für die Zielplattform enthält. Angenommen, Sie können kopiert haben die Dateien, damit der Compiler oder Link-Tool über die Eingabeaufforderung festlegen, ohne aufgerufen werden konnte die **Pfad** Umgebungsvariable entsprechend.